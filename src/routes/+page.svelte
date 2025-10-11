<script>
	import Landing from '$lib/components/Landing/Landing.svelte';
	import Road from '$lib/components/Road.svelte';
</script>

<main>
	<Landing />
	<div class="relative h-[230vh] lg:h-[300vh] xl:h-[360vh] w-full bg-grass-background overflow-x-hidden">
		<div class="absolute top-[-30px] lg:top-[-70px] xl:top-[-80px] left-3/5 lg:left-[65%] xl:left-3/5">
			<Road />
		</div>

		<!-- Content goes here -->
	</div>

	<div class="w-full flex flex-col justify-center items-center bg-grass-background gap-8">
		<h3 class="font-beachday text-white text-5xl">Sponsors</h3>
		<div
			class="relative h-screen w-full bg-center flex items-center justify-center bg-cover"
			style="background-image: url('/src/lib/assets/Lake.png');"
		>
			<!-- Sponsor logos go here! -->

			<h4 class=" font-beachday text-2xl">To be announced!</h4>
		</div>
	</div>
</main>
