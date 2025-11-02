<script>
	import Landing from '$lib/components/Landing/Landing.svelte';
	import Road from '$lib/components/Road.svelte';
	import FAQ from '$lib/components/FAQ/FAQ.svelte';
	import About from '$lib/components/About/About.svelte';
	import Tracks from '$lib/components/Tracks/Tracks.svelte';
	import Clubs from '$lib/components/Clubs.svelte';
	import lakeSrc from '$lib/assets/Lake.png';
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
			<div id="about-section" class="h-1/3">
				<About />
			</div>
			<div>
				<Tracks />
			</div>
			<div class="h-1/3">
				<FAQ />
			</div>
			<!-- <FAQ /> -->

			<div class="flex w-full flex-col items-center justify-center gap-8 bg-grass-background py-16">
				<h3 class="font-beachday text-5xl text-white">Sponsors</h3>
				<div
					class="relative flex min-h-[120vh] w-full items-center justify-center bg-cover bg-center"
					style="background-image: url({lakeSrc})"
				>
					<h4 class="font-beachday text-3xl">To be announced!</h4>
				</div>
			</div>
			<div class="h-[1200px]">
				<Clubs />
			</div>

			<!-- Cloud divider between clubs and footer -->
			<div class="w-full h-[5rem] xl:h-[10rem] 2xl:h-[12rem]">
				<CloudDivider height="20rem"/>
			</div>

			<div class="bg-blue-100"><Footer /></div>
			<div class="flex flex-col justify-center items-center gap-2 p-4 bg-black w-full text-center">
				<div class="flex justify-center items-center gap-2 flex-wrap">
					<p class="text-[10px] font-beachday text-white md:text-lg">Made with ❤️ by the Swamphacks Team</p>
					<p class="text-[8px] md:text-base text-white">© 2025</p>
				</div>
				<a
					href="https://github.com/MLH/mlh-policies/blob/main/code-of-conduct.md"
					target="_blank"
					rel="noopener noreferrer"
					class="font-beachday text-[10px] text-white/80 hover:text-white transition-colors duration-200 md:text-sm underline"
				>
					MLH Code of Conduct
				</a>
			</div>
		</div>
	</div>
</main>
