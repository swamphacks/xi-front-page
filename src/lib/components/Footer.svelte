<script lang="ts">
	import { onMount } from 'svelte';
	import backBg from '$lib/assets/back-bg.svg';
	import middleBg from '$lib/assets/middle-bg.svg';
	import frontBg from '$lib/assets/front-bg.svg';
	import Button from './Button/Button.svelte';
	import MovingPlane from './Landing/MovingPlane.svelte';
	import MovingCloud from './Landing/MovingCloud.svelte';
    import Link from './Link/Link.svelte';
	let backEl: HTMLImageElement;
	let middleEl: HTMLImageElement;
	let frontEl: HTMLImageElement;
	let sectionEl: HTMLElement;

	let isVisible = false;
	let rafId: number | null = null;

	const clamp = (v: number, min: number, max: number) => Math.max(min, Math.min(max, v));

	const tick = () => {
		const scrollY = window.scrollY;
		const vh = window.innerHeight;

		const rect = sectionEl.getBoundingClientRect();
		const sectionTop = scrollY + rect.top;
		const rel = clamp(scrollY - sectionTop, 0, rect.height + vh);
		const sBack = -0.1;
		const sMid = -0.3;
		const sFront = -0.5;

		const maxShift = 200;
		const tBack = clamp(rel * sBack, -maxShift, 0);
		const tMid = clamp(rel * sMid, -maxShift, 0);
		const tFront = clamp(rel * sFront, -maxShift, 0);

		if (backEl) backEl.style.transform = `translateY(${tBack}px)`;
		if (middleEl) middleEl.style.transform = `translateY(${tMid}px)`;
		if (frontEl) frontEl.style.transform = `translateY(${tFront}px)`;

		const visibleThreshold = vh * 0.45;
		const sectionVisibleAmount = clamp(vh - rect.top, 0, vh);
		isVisible = sectionVisibleAmount > visibleThreshold;

		rafId = requestAnimationFrame(tick);
	};

	onMount(() => {
		rafId = requestAnimationFrame(tick);
		const onResize = () => {};
		window.addEventListener('resize', onResize);

		return () => {
			if (rafId) cancelAnimationFrame(rafId);
			window.removeEventListener('resize', onResize);
		};
	});
</script>

<section bind:this={sectionEl} class="relative size-full h-[500px] overflow-hidden md:h-[800px] lg:h-[1000px] xl:h-[150vh]">
	<div
		class="absolute bottom-6 left-1/2 z-50 flex -translate-x-1/2 flex-col items-center justify-center gap-4 text-center will-change-transform md:bottom-40 w-full"
	>
		<p class="font-beachday text-2xl font-bold text-white md:text-6xl">Ready to Hack?</p>
		<Link href="https://app.swamphacks.com/events/53a94d27-4525-489b-8467-a0412722b313/application">
			<Button className="font-beachday text-md text-xl 2xl:text-3xl w-full">Register to Hack</Button
			>
		</Link>
	</div>

	<img
		src={backBg}
		alt="back layer"
		bind:this={backEl}
		class="pointer-events-none absolute bottom-0 left-0 z-0 w-full will-change-transform select-none md:-bottom-30 lg:-bottom-100 xl:-bottom-100"
	/>
	<img
		src={middleBg}
		alt="middle layer"
		bind:this={middleEl}
		class="pointer-events-none absolute bottom-27 left-0 z-10 w-full object-cover will-change-transform select-none md:bottom-10 2xl:bottom-50"
	/>

	<img
		src={frontBg}
		alt="front layer"
		bind:this={frontEl}
		class="pointer-events-none absolute bottom-0 left-0 z-30 w-full object-cover will-change-transform select-none md:-bottom-80"
	/>
	<MovingPlane duration={20} />
	
	<!-- <MovingCloud variant={1} duration={40} />
	<MovingCloud variant={1} duration={60} />
	<MovingCloud variant={2} duration={60} />
	<MovingCloud variant={2} duration={60} /> -->
</section>

<style>
	/* no colors; keep transforms smooth without lag */
	.will-change-transform {
		will-change: transform;
	}
</style>
