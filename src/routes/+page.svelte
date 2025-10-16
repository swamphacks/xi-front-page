<script>
	import BreakpointIndicator from '$lib/components/BreakpointIndicator.svelte';
	import Landing from '$lib/components/Landing/Landing.svelte';
	import Road from '$lib/components/Road.svelte';
	import FAQ from '$lib/components/FAQ/FAQ.svelte';
	import About from '$lib/components/About/About.svelte';
	import Tracks from '$lib/components/Tracks/Tracks.svelte';
	import Clubs from '$lib/components/Clubs.svelte';
	import lakeSrc from '$lib/assets/Lake.png';
	import Link from '$lib/components/Link/Link.svelte';
	import Button from '$lib/components/Button/Button.svelte';
</script>

<main class="overflow-x-hidden">
	<Landing />
	<div class="relative h-[490vh] w-full bg-grass-background lg:h-[430vh]">
		<div class="absolute top-[-20px] left-[90%] -translate-x-1/2 md:top-[-50px] md:left-3/4">
			<Road />
		</div>
		<div
			class="relative min-h-[200vh] w-full overflow-hidden bg-grass-background sm:min-h-[250vh] lg:min-h-[200vh] xl:min-h-[200vh]"
		>
			<div class="hidden lg:block">
				<Road />
			</div>

			<!-- Content 1 (About Us)-->
			<div class="h-1/3">
				<About />
			</div>

			<!-- Content 2 (Tracks)-->
			<Tracks />

			<!-- Content goes here -->

			<!-- About -->
			<!-- <About /> -->
			<!-- FAQ -->
			<div class="h-1/3">
				<FAQ />
			</div>
			<!-- <FAQ /> -->
		</div>

		<div class="flex w-full flex-col items-center justify-center gap-8 bg-grass-background py-16">
			<h3 class="font-beachday text-5xl text-white">Sponsors</h3>
			<div
				class="relative flex min-h-[120vh] w-full items-center justify-center bg-cover bg-center"
				style="background-image: url({lakeSrc})"
			>
				<h4 class="font-beachday text-2xl">To be announced!</h4>
			</div>
		</div>
	</div>
	<!-- Clubs -->
	<div class="flex h-[90vh] items-start justify-center overflow-hidden bg-grass-background">
		<Clubs />
	</div>
	<div class="flex h-[30vh] w-full flex-col items-center justify-center bg-grass-background">
		<h3 class="font-beachday text-5xl text-white md:text-6xl lg:text-8xl 2xl:text-9xl">
			Ready to hack?
		</h3>
		<Link href="https://app.swamphacks.com/events/53a94d27-4525-489b-8467-a0412722b313/application">
			<h3
				class="text-1xl font-outline mt-8 cursor-pointer font-beachday text-end-button hover:text-button-hover active:text-button-active-text md:text-6xl lg:text-8xl 2xl:text-7xl"
			>
				Register Now
			</h3>
		</Link>
	</div>
	<!-- <Clubs /> -->
</main>

<BreakpointIndicator />
