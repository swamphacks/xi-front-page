<script lang="ts">
	import Frame1 from '$lib/assets/Plane_Frame_1.svg?raw';
	import Frame2 from '$lib/assets/Plane_Frame_2.svg?raw';
	import Frame3 from '$lib/assets/Plane_Frame_3.svg?raw';

	import { onMount } from 'svelte';
	import { gsap } from 'gsap';

	let frame0: HTMLDivElement;
	let frame1: HTMLDivElement;
	let frame2: HTMLDivElement;

	onMount(() => {
		const frames = [frame0, frame1, frame2];

		// hide all frames initially
		gsap.set(frames, { autoAlpha: 0 });
		gsap.set(frame0, { autoAlpha: 1 });

		const frameDuration = 0.5; // 500ms per frame

		const tl = gsap.timeline({ repeat: -1 });

		// Ping-pong sequence: 0 → 1 → 2 → 1 → 0
		const sequence = [0, 1, 2, 1];

		sequence.forEach((idx) => {
			tl.call(
				() => {
					frames.forEach((f, i) => gsap.set(f, { autoAlpha: i === idx ? 1 : 0 }));
				},
				undefined,
				'+=' + frameDuration
			);
		});
	});
</script>

<div class="relative h-[200px] w-[200px]">
	<div bind:this={frame0} class="absolute inset-0">
		{@html Frame1}
	</div>
	<div bind:this={frame1} class="absolute inset-0">
		{@html Frame2}
	</div>
	<div bind:this={frame2} class="absolute inset-0">
		{@html Frame3}
	</div>
</div>
