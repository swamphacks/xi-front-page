<script lang="ts">
	import { gsap } from 'gsap';
	import CenturyTower from '$lib/assets/CenturyTower.svg?raw';
	import Bell from '$lib/assets/Bell.svg?raw';
	import Clapper from '$lib/assets/Clapper.svg?raw';

	let bell: HTMLButtonElement;
	let clapper: HTMLDivElement;

	function ring() {
		const tl = gsap.timeline();

		gsap.set(bell, { rotate: 0, transformOrigin: 'top center' });
		gsap.set(clapper, { rotate: 0, transformOrigin: 'top center' });

		tl.to(bell, {
			rotate: 12,
			duration: 0.3,
			ease: 'sine.inOut'
		})
			.to(bell, {
				rotate: -12,
				duration: 0.6,
				yoyo: true,
				repeat: 4,
				ease: 'sine.inOut'
			})
			.to(bell, {
				rotate: 0,
				duration: 1.2,
				ease: 'power2.out'
			});

		tl.to(
			clapper,
			{
				rotate: -10,
				duration: 0.3,
				ease: 'sine.inOut'
			},
			0.05 // minimal lag behind bell
		)
			.to(
				clapper,
				{
					rotate: 10,
					duration: 0.6,
					yoyo: true,
					repeat: 4,
					ease: 'sine.inOut'
				},
				'>'
			)
			.to(
				clapper,
				{
					rotate: 0,
					duration: 1.2,
					ease: 'power2.out'
				},
				'>'
			);
	}
</script>

<div class="relative inline-block">
	<!-- Clapper (behind) -->
	<div
		bind:this={clapper}
		class="absolute top-[198px] left-[51%] z-0 h-auto w-[10px] [&_svg]:block [&_svg]:h-auto [&_svg]:w-full"
	>
		{@html Clapper}
	</div>

	<!-- Bell (middle, clickable) -->
	<button
		bind:this={bell}
		on:click={ring}
		class="absolute top-[7%] left-[38%] z-10 h-auto w-[92px] cursor-pointer [&_svg]:block [&_svg]:h-auto [&_svg]:w-full"
	>
		{@html Bell}
	</button>

	<!-- Tower (front) -->
	<div
		class="pointer-events-none relative z-20 h-auto w-[300px] [&_svg]:block [&_svg]:h-auto [&_svg]:w-full"
	>
		{@html CenturyTower}
	</div>
</div>
