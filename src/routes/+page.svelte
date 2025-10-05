<script>
	// import ScrollablePath from "$lib/components/scrollablepath/ScrollablePath.svelte";
	import BushWall from '$lib/assets/BushWall.png';
	import SwampHacksTitle from '$lib/assets/SwampHacks Title.png';
	import CenturyTower from '$lib/assets/CenturyTower.png';
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
			class="pointer-events-none absolute bottom-0 left-[16%] h-[30%] sm:h-[90%] w-auto max-w-full object-contain select-none"
		/>

		<!-- Bush Wall -->
		<img
			src={BushWall}
			alt="Bush wall"
			class="pointer-events-none absolute bottom-[-10px] left-0 h-[7%] sm:h-1/8 w-full object-cover select-none"
		/>
	</div>

	<div class="h-screen w-full bg-grass-background"></div>
</main>

<!-- <p class="title-text text-center m-4 sm:m-6 text-5xl sm:text-7xl 2xl:text-8xl font-bold tracking-wide leading-14 md:leading-20 2xl:leading-32">SwampHacks XI</p> -->
<!-- 
<ScrollablePath /> -->
