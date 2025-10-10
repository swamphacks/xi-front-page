<script>
	// import ScrollablePath from "$lib/components/scrollablepath/ScrollablePath.svelte";
	import BushWall from '$lib/assets/BushWall.png';
	import SwampHacksTitle from '$lib/assets/SwampHacks Title.png';
	import CenturyTower from '$lib/assets/CenturyTower.png';
	import Bush1 from '$lib/assets/svg-illustrations/svg bush_1.svg';
	import Bush2 from '$lib/assets/svg-illustrations/svg bush_2.svg';
	import Bush3 from '$lib/assets/svg-illustrations/svg bush_3.svg';
	import Bush4 from '$lib/assets/svg-illustrations/svg bush_4.svg';
</script>

<main>
	<div class="relative h-screen w-full overflow-hidden bg-sky-background">
		<!-- Title + Button Container -->
		<div
			class="absolute top-1/2 left-1/2 flex
				   -translate-x-1/2 -translate-y-1/2 flex-col items-center
				   gap-4 space-y-6 select-none md:top-[30%] md:left-2/5 md:translate-x-0 md:translate-y-0 w-full sm:w-fit"
		>
			<img
				src={SwampHacksTitle}
				alt="SwampHacks Title"
				class="pointer-events-none w-4/5 sm:w-fit md:h-1/6"
			/>

			<!-- Button -->
			<div class="flex w-full flex-col items-center justify-center gap-4">
				<button class="w-1/2 cursor-pointer bg-button-primary py-4 rounded-md"> Register To Hack </button>

				<button class="w-1/2 cursor-pointer bg-button-primary py-4 rounded-md"> Apply to Mentor </button>
			</div>
		</div>

		<!-- Century Tower -->
		<img
			src={CenturyTower}
			alt="Century Tower"
			class="z-2 pointer-events-none absolute bottom-0 left-[16%] h-[30%] sm:h-[90%] w-auto max-w-full object-contain select-none"
		/>

		<!-- SVG Bushes at bottom -->
		<div class="absolute -bottom-2 left-0 w-full flex items-end pointer-events-none select-none">
			{#each Array(24) as _, i}
				{@const bushIndex = i % 4}
				{@const bushSrc = [Bush1, Bush2, Bush3, Bush4][bushIndex]}
				<img 
					src={bushSrc} 
					alt="Bush {bushIndex + 1}" 
					class="h-6 sm:h-8 md:h-10 lg:h-12 xl:h-16 w-auto object-contain flex-shrink-0 -ml-1 sm:-ml-2 md:-ml-3 lg:-ml-4 xl:-ml-5" 
				/>
			{/each}
		</div>

	</div>

	<div class="h-screen w-full bg-grass-background"></div>
</main>

<!-- <p class="title-text text-center m-4 sm:m-6 text-5xl sm:text-7xl 2xl:text-8xl font-bold tracking-wide leading-14 md:leading-20 2xl:leading-32">SwampHacks XI</p> -->
<!-- 
<ScrollablePath /> -->
