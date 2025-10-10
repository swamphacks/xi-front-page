<script>
	import Landing from '$lib/components/Landing/Landing.svelte';
	import Road from '$lib/components/Road.svelte';
</script>

<main>
	<Landing />
	<div class="relative h-[400vh] w-full bg-grass-background">
		<div class="absolute top-[-20px] left-[90%] -translate-x-1/2 md:top-[-50px] md:left-3/4">
			<Road />
		</div>

		<!-- Content goes here -->
	</div>

	<div
		class="relative h-screen w-full bg-center bg-grass-background"
		style="background-image: url('/src/lib/assets/Lake.png');"
	>
		<!-- Optional: overlay content -->
	</div>
</main>
