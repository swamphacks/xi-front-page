<script lang="ts">
	import { gsap } from 'gsap';
	import CenturyTower from '$lib/assets/CenturyTower.svg?raw';
	import Bell from '$lib/assets/Bell.svg?raw';
	import Clapper from '$lib/assets/Clapper.svg?raw';

	let bell: HTMLButtonElement;
	let clapper: HTMLDivElement;

	function ring() {
		const tl = gsap.timeline();

		// reset transforms
		gsap.set([bell, clapper], { rotate: 0, transformOrigin: 'top center' });

		// main ringing motion
		tl.to(bell, {
			rotate: 15,
			duration: 0.25,
			yoyo: true,
			repeat: 8,
			ease: 'sine.inOut'
		}).to(
			bell,
			{
				rotate: 0,
				duration: 1.2,
				ease: 'elastic.out(1, 0.3)'
			},
			'>'
		);

		// clapper motion (slightly delayed and opposite phase)
		tl.to(
			clapper,
			{
				rotate: -20,
				duration: 0.25,
				yoyo: true,
				repeat: 8,
				ease: 'sine.inOut'
			},
			0.05 // small delay so it lags behind
		).to(
			clapper,
			{
				rotate: 0,
				duration: 1.2,
				ease: 'elastic.out(1, 0.3)'
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

	<!-- Bell (middle) -->
	<button
		bind:this={bell}
		on:click={ring}
		class="absolute top-[7%] left-[38%] z-10 h-auto w-[92px] cursor-pointer [&_svg]:block [&_svg]:h-auto [&_svg]:w-full"
	>
		{@html Bell}
	</button>

	<!-- Tower (in front) -->
	<div
		class=" pointer-events-none relative z-20 h-auto w-[300px] [&_svg]:block [&_svg]:h-auto [&_svg]:w-full"
	>
		{@html CenturyTower}
	</div>
</div>
