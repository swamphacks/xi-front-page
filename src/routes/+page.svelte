<script>
	import BreakpointIndicator from '$lib/components/BreakpointIndicator.svelte';
	import Landing from '$lib/components/Landing/Landing.svelte';
	import Road from '$lib/components/Road.svelte';
</script>

<main>
	<Landing />
	<div
		class="relative min-h-[200vh] w-full overflow-hidden bg-grass-background sm:min-h-[250vh] lg:min-h-[200vh] xl:min-h-[200vh]"
	>
		<Road />

		<!-- Content 1 (About Us)-->
		<div></div>

		<!-- Content 2 (Tracks)-->
		<div></div>

		<!-- Content 3 (FAQs)-->
		<div></div>
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
