<script lang="ts">
	import Bush1 from '$lib/assets/Bush_1.svg';
	import Bush2 from '$lib/assets/Bush_2.svg';
	import Bush3 from '$lib/assets/Bush_3.svg';
	import Bush4 from '$lib/assets/Bush_4.svg';
</script>

<div class="pointer-events-none absolute -bottom-2 left-0 flex w-full items-end select-none">
	{#each Array(48) as _, i}
		{@const bushIndex = i % 4}
		{@const bushSrc = [Bush1, Bush2, Bush3, Bush4][bushIndex]}

		<img
			src={bushSrc}
			alt="Bush {bushIndex + 1}"
			class="-ml-2 h-10 w-auto flex-shrink-0 object-contain sm:-ml-2 sm:h-8 md:-ml-3 md:h-10 lg:-ml-4 lg:h-12 xl:-ml-5 xl:h-16"
		/>
	{/each}
</div>
