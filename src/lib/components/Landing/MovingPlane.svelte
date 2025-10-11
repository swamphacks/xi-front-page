<script lang="ts">
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';
	import Plane from './Plane.svelte';

	export let duration: number = 10; // seconds per pass
	export let offset: number = 700; // extra distance to travel offscreen

	let planeEl: HTMLDivElement;

	onMount(() => {
		const screenWidth = window.innerWidth;
		const planeWidth = planeEl.offsetWidth;

		// Start offscreen to the right
		gsap.set(planeEl, { x: screenWidth, opacity: 1 });

		// Animate right → left, looping forever
		gsap.to(planeEl, {
			x: -(planeWidth + offset),
			duration,
			repeat: -1,
			ease: 'linear'
		});
	});
</script>

<!-- Plane container -->
<div bind:this={planeEl} class="absolute top-0 z-48 scale-[0.032] opacity-0 md:scale-[0.05]">
	<Plane />
</div>
