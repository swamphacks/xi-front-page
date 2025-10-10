<script lang="ts">
	import BushWall from '$lib/assets/BushWall.png';
	import { onMount } from 'svelte';
	import CenturyTower from './CenturyTower.svelte';
	import Plane from './Plane.svelte';
	import { gsap } from 'gsap';

	let planeEl: HTMLDivElement;

	onMount(() => {
		const screenWidth = window.innerWidth;
		const planeWidth = planeEl.offsetWidth;

		// Start fully offscreen to the right
		gsap.set(planeEl, { x: screenWidth, opacity: 1 });

		// Animate to fully offscreen left
		gsap.to(planeEl, {
			x: -(planeWidth + 700), // end position offscreen left
			duration: 30, // duration in seconds
			repeat: -1, // loop infinitely
			ease: 'linear' // constant speed
		});
	});
</script>

<div class="relative h-screen w-full overflow-hidden bg-sky-background">
	<div bind:this={planeEl} class="absolute top-0 scale-[0.032] md:scale-[0.05] opacity-0">
		<Plane />
	</div>

	<!-- Title + Button Container -->
	<div
		class="absolute top-1/2 left-1/2 z-50 flex
		   w-full -translate-x-1/2 -translate-y-1/2 flex-col
		   items-center gap-4 space-y-6 select-none sm:w-fit md:top-[30%] md:left-2/5 md:translate-x-0 md:translate-y-0"
	>
		<div class="flex flex-col items-center justify-center gap-2">
			<h1 class="font-beachday text-5xl md:text-6xl lg:text-8xl">SwampHacks XI</h1>
			<h2 class="font-beachday text-3xl md:text-4xl lg:text-5xl">January 23rd - 25th</h2>
			<h3 class="font-beachday text-2xl md:text-3xl lg:text-4xl">Newell Hall</h3>
		</div>

		<!-- Button -->
		<div class="flex w-full flex-col items-center justify-center gap-4">
			<button
				class="w-1/2 cursor-pointer rounded-md bg-button-primary py-3 font-beachday text-lg transition-all duration-100 hover:scale-105 md:py-4 md:text-2xl"
			>
				Register To Hack
			</button>

			<button
				class="w-1/2 cursor-pointer rounded-md bg-button-primary py-3 font-beachday text-lg transition-all duration-100 hover:scale-105 md:py-4 md:text-2xl"
			>
				Apply to Mentor
			</button>
		</div>
	</div>

	<div
		class="absolute bottom-0 left-[16%] origin-bottom-left translate-y-[3px] scale-[0.13] md:scale-[0.45]"
	>
		<CenturyTower />
	</div>

	<!-- Bush Wall -->
	<img
		src={BushWall}
		alt="Bush wall"
		class="pointer-events-none absolute bottom-[-10px] left-0 h-[7%] w-full object-cover select-none sm:h-1/8"
	/>
</div>
