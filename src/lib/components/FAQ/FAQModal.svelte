<script lang="ts">
	import { slide } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';

	const { onClose, title, faqs } = $props();

	let activeIndex: number | null = $state(null);

	function toggle(index: number | null) {
		activeIndex = index;
	}
	function linkifyText(text: string) {
		text = text.replace(
			/([\w.-]+@[\w.-]+\.\w+)/g,
			'<a href="mailto:$1" class="underline": underline>$1</a>'
		);
		text = text.replace(
			'MentorLink',
			'<a href="https://forms.gle/yiKGESaMMdHbRRTu5" target="_blank" class="underline": underline>Here</a>'
		);
		text = text.replace(
			'Click here to sign up to volunteer!',
			'<a href="https://swamphack.notion.site/2af3b41de22f80d7a5d9e1ddecf26004?pvs=105?" target="_blank" rel="noopener noreferrer" class="underline text-blue-600 hover:text-blue-800">Click here to sign up to volunteer!</a>'
		);
		return text;
	}
</script>

<div
	class="fixed inset-0 z-100 flex items-center justify-center bg-black/50"
	role="button"
	tabindex="0"
	onkeydown={(event) => {
		if (event.key === 'Escape') {
			onClose();
		}
	}}
	onclick={(e: any) => e.target === e.currentTarget && onClose()}
>
	<div
		class="absolute m-3 max-h-screen w-[90vw] max-w-2xl overflow-hidden rounded-lg bg-white p-6 shadow-lg lg:max-w-xl"
	>
		<h1 class="justify-center text-center text-xl font-bold">{title}</h1>
		<button
			class="absolute top-2 right-2 cursor-pointer px-5 py-2.5 text-xl text-gray-600 hover:text-red-800"
			onclick={() => onClose()}
		>
			&times;
		</button>
		{#each faqs as faq, index}
			<div class="border-b border-gray-200 last:border-b-0">
				<button
					class="flex w-full cursor-pointer items-center justify-between bg-gray-50 p-4 text-left font-semibold hover:bg-gray-100 focus:outline-none"
					onclick={() => {
						if (activeIndex !== index) {
							toggle(index);
						} else toggle(null);
					}}
				>
					<span>{faq.question}</span>
					<span
						class="transform transition-transform duration-300"
						class:rotate-180={activeIndex === index}
					>
						▼
					</span>
				</button>

				{#if activeIndex === index}
					<div
						class="bg-white px-6 pt-3 pb-6"
						transition:slide={{ duration: 300, easing: quintOut }}
					>
						<p class="leading-relaxed whitespace-pre-line text-gray-700">
							{@html linkifyText(faq.answer)}
						</p>
					</div>
				{/if}
			</div>
		{/each}
	</div>
</div>
