<script lang="ts">
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';
	import Cloud from './Cloud.svelte';

	export let variant: number = 1;
	export let duration: number = 40; // seconds to cross screen

	let cloudEl: HTMLDivElement;

	const isMobile = typeof window !== 'undefined' && window.innerWidth < 768;

	const maxY = isMobile ? 40 : 30;
	const minY = 0;

	const randomY = () => {
		const padding = 20;
		return (
			padding + ((Math.random() * (maxY - minY) + minY) / 100) * (window.innerHeight - padding)
		);
	};

	const randomScale = () =>
		isMobile ? Math.random() * (0.05 - 0.02) + 0.02 : Math.random() * (0.08 - 0.06) + 0.06;

	onMount(() => {
		if (!cloudEl) return;

		const cloudWidth = cloudEl.offsetWidth;

		// Initial spawn
		const startScale = randomScale();
		const startX = Math.random() * (window.innerWidth - cloudWidth * startScale);
		const startY = randomY();

		gsap.set(cloudEl, {
			x: startX,
			y: startY,
			scale: startScale,
			opacity: 0,
			transformOrigin: 'top left'
		});

		// Fade in
		gsap.to(cloudEl, { opacity: 1, duration: 1 });

		// Animate with repeat: -1 (no recursion)
		gsap.to(cloudEl, {
			x: window.innerWidth + cloudWidth,
			duration,
			ease: 'linear',
			repeat: -1,
			onRepeat: () => {
				// Reset to left offscreen and random Y + scale
				const newScale = randomScale();
				gsap.set(cloudEl, {
					x: -cloudWidth * newScale,
					y: randomY(),
					scale: newScale
				});
			}
		});
	});
</script>

<div bind:this={cloudEl} class="absolute top-0 z-10 opacity-0">
	<Cloud {variant} />
</div>
