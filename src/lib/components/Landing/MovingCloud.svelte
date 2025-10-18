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

	// Helper to return a promise when tween completes
	const tween = (target: any, vars: gsap.TweenVars) =>
		new Promise<void>((resolve) => gsap.to(target, { ...vars, onComplete: resolve }));

	onMount(async () => {
		if (!cloudEl) return;

		const cloudWidth = cloudEl.offsetWidth;

		// ----- First animation (spawn somewhere on screen) -----
		const startScale = randomScale();
		const startX = Math.random() * (window.innerWidth - cloudWidth * startScale);
		const startY = randomY();

		gsap.set(cloudEl, {
			x: startX,
			y: startY,
			scale: startScale,
			transformOrigin: 'top left'
		});

		// Fade in

		const move = tween(cloudEl, {
			x: window.innerWidth + cloudWidth,
			duration,
			ease: 'linear'
		});

		const fadeIn = tween(cloudEl, {
			opacity: 1,
			duration: 3
		});

		// Move to right edge
		await Promise.all([move, fadeIn]);

		// ----- Infinite looping timeline after first pass -----
		const loopTimeline = gsap.timeline({ repeat: -1 });

		loopTimeline
			.set(cloudEl, {
				opacity: 0,
				x: -cloudWidth,
				y: randomY(),
				scale: randomScale()
			})
			.to(cloudEl, { opacity: 1, duration: 1 })
			.to(cloudEl, {
				x: window.innerWidth + cloudWidth,
				duration,
				ease: 'linear'
			});
	});
</script>

<div bind:this={cloudEl} class="absolute top-0 z-10 opacity-0">
	<Cloud {variant} />
</div>
