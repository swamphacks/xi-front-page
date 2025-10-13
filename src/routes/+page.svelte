<script>
	import BreakpointIndicator from '$lib/components/BreakpointIndicator.svelte';
	import Landing from '$lib/components/Landing/Landing.svelte';
	import Road from '$lib/components/Road.svelte';
	import FAQ from '$lib/components/FAQ/FAQ.svelte';
	import About from '$lib/components/About.svelte';
</script>

<main>
	<Landing />
	<div class="relative h-[400vh] w-full bg-grass-background">
		<div class="absolute top-[-20px] left-[90%] -translate-x-1/2 md:top-[-50px] md:left-3/4">
			<Road />
		</div>
		<FAQ/>
		<!-- Content goes here -->
		
		<!-- About -->
		 <div class="h-1/3">
			<About />
			
		 </div>
		<!-- <About /> -->
	</div>

	<div class="flex w-full flex-col items-center justify-center gap-8 bg-grass-background py-16">
		<h3 class="font-beachday text-5xl text-white">Sponsors</h3>
		<div
			class="relative flex min-h-[120vh] w-full items-center justify-center bg-cover bg-center"
			style="background-image: url('/src/lib/assets/Lake.png');"
		>
			<h4 class="font-beachday text-2xl">To be announced!</h4>
		</div>
	</div>
</main>

<BreakpointIndicator />
