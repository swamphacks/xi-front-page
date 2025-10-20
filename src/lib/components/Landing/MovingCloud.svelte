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
	onMount(async () => {
		if (!cloudEl) return;

		const cloudWidth = cloudEl.offsetWidth;
		const startScale = randomScale();

		if (isMobile) {
			gsap.set(cloudEl, {
				x: Math.random() * (window.innerWidth - cloudWidth * startScale),
				y: randomY(),
				scale: startScale,
				opacity: 1,
				transformOrigin: 'top left'
			});

			return;
		}

		gsap.set(cloudEl, {
			x: Math.random() * (window.innerWidth - cloudWidth * startScale),
			y: randomY(),
			scale: startScale,
			opacity: 0,
			transformOrigin: 'top left'
		});

		const masterTimeline = gsap.timeline();

		masterTimeline.to(
			cloudEl,
			{
				x: window.innerWidth + cloudWidth,
				duration,
				ease: 'linear'
			},
			0
		);

		masterTimeline.to(
			cloudEl,
			{
				opacity: 1,
				duration: 3
			},
			0
		);

		masterTimeline.set(cloudEl, {
			opacity: 0,
			x: -cloudWidth,
			y: randomY(),
			scale: randomScale()
		});

		masterTimeline.to(cloudEl, { opacity: 1, duration: 1 }).to(cloudEl, {
			x: window.innerWidth + cloudWidth,
			duration,
			ease: 'linear',
			repeat: -1,
			onRepeat: () => {
				gsap.set(cloudEl, {
					opacity: 0,
					x: -cloudWidth,
					y: randomY(),
					scale: randomScale()
				});
				gsap.to(cloudEl, { opacity: 1, duration: 1 }); // Fade back in
			}
		});
	});
</script>

<div bind:this={cloudEl} class="absolute top-0 z-10 opacity-0">
	<Cloud {variant} />
</div>
