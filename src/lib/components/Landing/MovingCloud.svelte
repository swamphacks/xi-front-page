<script lang="ts">
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';
	import Cloud from './Cloud.svelte';

	export let variant: number = 1;

	export let duration = 40; // seconds to cross screen

	let cloudEl: HTMLDivElement;

	const isMobile = typeof window !== 'undefined' && window.innerWidth < 768;

    let maxY = isMobile ? 40 : 30;
    let minY = 0;

	const randomY = () => {
		const padding = 20;
		return (
			padding + ((Math.random() * (maxY - minY) + minY) / 100) * (window.innerHeight - padding)
		);
	};

	const randomScale = () =>
		isMobile ? Math.random() * (0.05 - 0.02) + 0.02 : Math.random() * (0.08 - 0.06) + 0.06;

	const initialX = (scale: number) => {
		const cloudWidth = cloudEl.offsetWidth * scale;
		return isMobile
			? Math.random() * (window.innerWidth - cloudWidth)
			: Math.random() * window.innerWidth;
	};

	onMount(() => {
		const startScale = randomScale();
		const startX = initialX(startScale);
		const startY = randomY();

		// Initial random spawn (both random X and Y)
		gsap.set(cloudEl, {
			x: startX,
			y: startY,
			scale: startScale,
			opacity: 0,
			transformOrigin: 'top left'
		});

		// Fade in clouds
		gsap.to(cloudEl, { opacity: 1, duration: 1 });

		const animate = (firstRun = false) => {
			const scale = randomScale();
			const width = cloudEl.offsetWidth * scale;
			const endX = window.innerWidth + width;

			// For the first run, start from the current position to the right edge
            // For subsequent runs, start from just offscreen left
			if (!firstRun) {
				gsap.set(cloudEl, {
					x: -width,
					y: randomY(),
					scale
				});
			}

			gsap.to(cloudEl, {
				x: endX,
				duration,
				ease: 'linear',
				onComplete: () => animate(false)
			});
		};

		// Run the first animation starting from the middle position
		animate(true);
	});
</script>

<div bind:this={cloudEl} class="absolute opacity-0">
	<Cloud {variant} />
</div>
