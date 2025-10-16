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
		bind:this="{clapper}"
		class="absolute top-[198px] left-[51%] z-0 h-auto w-[10px] [&_svg]:block [&_svg]:h-auto [&_svg]:w-full"
	>
		{@html Clapper}
	</div>

	<!-- Bell (middle, clickable) -->
	<button
		bind:this="{bell}"
		on:click="{ring}"
		class="absolute top-[7%] left-[38%] z-10 h-auto w-[92px] cursor-pointer [&_svg]:block [&_svg]:h-auto [&_svg]:w-full"
	>
		{@html Bell}
	</button>

	<!-- MLH banner -->
	<div
		class="absolute top-[21.3%] left-[34%] z-30 h-auto w-[200px] cursor-pointer [&_svg]:block [&_svg]:h-auto [&_svg]:w-full"
	>
		<a
			id="mlh-trust-badge"
			style="display: block; max-width: 300px; min-width: 120px; width: 10%; z-index: 10000"
			href="https://mlh.io/na?utm_source=na-hackathon&utm_medium=TrustBadge&utm_campaign=2026-season&utm_content=white"
			target="_blank"
			><img
				src="https://s3.amazonaws.com/logged-assets/trust-badge/2026/mlh-trust-badge-2026-white.svg"
				alt="Major League Hacking 2026 Hackathon Season"
				style="width: 100%"
		/></a>
	</div>

	<!-- Tower (front) -->
	<div
		class="pointer-events-none relative z-20 h-auto w-[300px] [&_svg]:block [&_svg]:h-auto [&_svg]:w-full"
	>
		{@html CenturyTower}
	</div>
</div>
