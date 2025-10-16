<script lang="ts">
	export let src = '$lib/assets/Hippodrome.png';
	export let alt = 'Button Image';
	export let title = 'Title';
	export let onClick;
</script>

<div class="m-4 flex w-max items-center justify-center lg:w-2/5">
	<div
		class="group flex size-full transform justify-center gap-2 border-2 border-dashed bg-white p-2 shadow-2xl transition-transform duration-300 hover:scale-105 hover:-rotate-1"
		onclick={onClick}
		onkeydown={(event) => {}}
		role="button"
		tabindex="0"
	>
		<div class="relative flex h-full w-full flex-col gap-4 bg-[#E8DCC4] p-6">
			<h3 class="cursor-default text-center font-beachday text-4xl text-gray-800">{title}</h3>
			<img
				{src}
				{alt}
				class="block h-auto w-max justify-center object-contain opacity-90 group-hover:opacity-100"
			/>
		</div>
	</div>
</div>
