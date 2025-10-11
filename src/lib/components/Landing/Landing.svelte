<script lang="ts">
	import BushWall from '$lib/assets/BushWall.png';
	import CenturyTower from './CenturyTower.svelte';
	import MovingCloud from './MovingCloud.svelte';
	import MovingPlane from './MovingPlane.svelte';
</script>

<div class="relative h-screen w-full overflow-hidden bg-sky-background">
	<MovingPlane duration={30} />

	<!-- Clouds -->

	<MovingCloud variant={1} duration={85} />
	<MovingCloud variant={2} duration={100} />
	<MovingCloud variant={3} duration={110} />
	<MovingCloud variant={4} duration={90} />
	<MovingCloud variant={1} duration={85} />
	<MovingCloud variant={3} duration={100} />

	<!-- Title + Button Container -->
	<div
		class="flex flex-col justify-center items-center h-full gap-6 z-50"
	>
		<div class="flex flex-col items-center justify-center gap-2">
			<h1 class="font-beachday text-5xl md:text-6xl lg:text-8xl">SwampHacks XI</h1>
			<h2 class="font-beachday text-3xl md:text-4xl lg:text-5xl">January 23rd - 25th</h2>
			<h3 class="font-beachday text-2xl md:text-3xl lg:text-4xl">Newell Hall</h3>
		</div>

		<!-- Button -->
		<div class="flex w-full flex-col items-center justify-center gap-4">
			<button
				class="cursor-pointer rounded-md bg-button-primary py-3 px-12 font-beachday text-lg transition-all duration-100 hover:scale-105 md:py-4 md:text-2xl"
			>
				Register To Hack
			</button>

			<button
				class="cursor-pointer rounded-md bg-button-primary py-3 px-12 font-beachday text-lg transition-all duration-100 hover:scale-105 md:py-4 md:text-2xl"
			>
				Apply to Mentor
			</button>
		</div>
	</div>

	<div
		class="absolute bottom-0 left-[4%] md:left-[16%] z-49 origin-bottom-left translate-y-[3px] scale-[0.25] md:scale-[0.45]"
	>
		<CenturyTower />
	</div>

	<!-- Bush Wall -->
	<!-- TODO: Replace this with the individual bushes but lined up together might be nicer -->
	<img
		src={BushWall}
		alt="Bush wall"
		class="pointer-events-none absolute bottom-[-10px] left-0 z-50 h-[7%] w-full object-cover select-none sm:h-1/8"
	/>
</div>
