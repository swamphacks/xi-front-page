<script>
	import Landing from '$lib/components/Landing/Landing.svelte';
	import Road from '$lib/components/Road.svelte';
	import FAQ from '$lib/components/FAQ/FAQ.svelte';
	import About from '$lib/components/About/About.svelte';
	import Tracks from '$lib/components/Tracks/Tracks.svelte';
	import Clubs from '$lib/components/Clubs.svelte';
	import Sponsors from '$lib/components/Sponsors.svelte';
	import Link from '$lib/components/Link/Link.svelte';
	import { onMount } from 'svelte';
	import Footer from '$lib/components/Footer.svelte';
	import CloudDivider from '$lib/components/CloudDivider.svelte';

	let isMobile = false;

	const checkMobile = () => {
		isMobile = window.innerWidth < 1024;
	};

	onMount(() => {
		checkMobile();
		window.addEventListener('resize', checkMobile);
		return () => window.removeEventListener('resize', checkMobile);
	});
	
</script>

<main class="w-screen overflow-x-hidden">
	<Landing />
	<div class="relative min-h-[500vh] w-full bg-grass-background lg:min-h-[430vh]">
		<div
			class="relative min-h-[200vh] w-full overflow-hidden bg-grass-background sm:min-h-[250vh] lg:min-h-[200vh] xl:min-h-[200vh]"
		>
			{#if !isMobile}
				<Road />
			{/if}

			<!-- Content 1 (About Us)-->
			<div class="h-1/3">
				<About />
			</div>
			<div>
				<Tracks />
			</div>
			<div class="h-1/3">
				<FAQ />
		</div>
		<!-- <FAQ /> -->
		
		<Sponsors />
		
		<div class="h-[1200px]">
				<Clubs />
			</div>

			<!-- Cloud divider between clubs and footer -->
			<div class="w-full h-[5rem] xl:h-[10rem] 2xl:h-[12rem]">
				<CloudDivider height="20rem"/>
			</div>

			<div class="bg-blue-100"><Footer /></div>
			<div class="flex justify-center items-center gap-2 p-4 bg-black w-full text-center">
				<p class="text-[10px] font-beachday text-white md:text-lg">Made with ❤️ by the Swamphacks Team</p>
				<p class="text-[8px] md:text-base text-white">© 2025</p>
			</div>
		</div>
	</div>
</main>
