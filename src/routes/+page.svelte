<script>
	// import ScrollablePath from "$lib/components/scrollablepath/ScrollablePath.svelte";
	import BushWall from '$lib/assets/BushWall.png';
	import SwampHacksTitle from '$lib/assets/SwampHacks Title.png';
	import CenturyTower from '$lib/assets/CenturyTower.png';
</script>

<main>
	<div class="relative h-screen w-full overflow-hidden bg-sky-background">
		<img
			src={SwampHacksTitle}
			alt="SwampHacks Title"
			class="absolute top-1/2 left-1/2 w-4/5 -translate-x-1/2
			   -translate-y-1/2 sm:w-fit md:top-1/3 md:left-2/5 md:h-1/6 md:translate-x-0 md:translate-y-0 select-none pointer-events-none"
		/>

		<img
			src={CenturyTower}
			alt="Century Tower"
			class="absolute bottom-0 left-[16%] h-[90%] w-auto max-w-full object-contain select-none pointer-events-none"
		/>

		<img
			src={BushWall}
			alt="Bush wall"
			class="absolute bottom-[-10px] left-0 h-1/8 w-full object-cover select-none pointer-events-none"
		/>
	</div>

	<div class="h-screen w-full bg-grass-background"></div>
</main>

<!-- <p class="title-text text-center m-4 sm:m-6 text-5xl sm:text-7xl 2xl:text-8xl font-bold tracking-wide leading-14 md:leading-20 2xl:leading-32">SwampHacks XI</p> -->
<!-- 
<ScrollablePath /> -->
