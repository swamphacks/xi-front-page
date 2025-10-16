<script lang="ts">
    import { gsap } from "gsap";
    import { MotionPathPlugin } from "gsap/MotionPathPlugin";
    import { ScrollTrigger } from "gsap/ScrollTrigger";

	import { onMount } from "svelte";

    let car: HTMLDivElement;
    let path: SVGPathElement;
    
    onMount(() => {
        gsap.registerPlugin(MotionPathPlugin, ScrollTrigger);
        
        let rotateTo = gsap.quickTo(car, "rotation");
        let prevDirection = 0;

        const tween = gsap.to(car, {
            scrollTrigger: {
               trigger: path,
               start: "top center",
               end: "bottom center",
               scrub: 0.5,
               markers: true,
               onUpdate: self => {
                 if (prevDirection !== self.direction) { // change direction
                   rotateTo(self.direction === 1 ? 0 : -180);
                   prevDirection = self.direction;
                 }    
                }
            },
            immediateRender: true,
            motionPath: {
              path: path,
              align: path,
              alignOrigin: [0.5, 0.5],
              autoRotate: 90,
            }
        });
    })
</script>

<div bind:this={car} class="w-16 h-24 xl:w-48 xl:h-64 bg-amber-200 rounded-lg"></div>

<svg fill="none" xmlns="http://www.w3.org/2000/svg" height="100%" width="100%" viewBox="0 0 1300 3000">
  <path bind:this={path} d="M143.78,431.83c103.76,235.99,223.54,324.48,318.04,360c143.34,53.87,223.51-16.03,379,51.84 c136.54,59.6,292.87,208.71,272.99,325.44c-25.74,151.18-320.87,94.36-612.23,336.96c-155.68,129.63-367.75,392.59-331.29,624.96 c43.59,277.79,443.64,520.03,985.93,492.48" stroke="black" stroke-width="8"/>
</svg>

