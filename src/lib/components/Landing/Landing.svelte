<script lang="ts">
	import Button from '../Button.svelte';
	import Link from '../Link.svelte';
	import BushWall from './BushWall.svelte';
	import CenturyTower from './CenturyTower.svelte';
	import MovingCloud from './MovingCloud.svelte';
	import MovingPlane from './MovingPlane.svelte';
</script>

<section class="relative h-screen w-full overflow-hidden bg-sky-background">
	<MovingPlane duration={30} />

	<!-- Clouds -->
	<MovingCloud variant={1} duration={85} />
	<MovingCloud variant={2} duration={100} />
	<MovingCloud variant={3} duration={110} />
	<MovingCloud variant={4} duration={90} />
	<MovingCloud variant={1} duration={85} />
	<MovingCloud variant={3} duration={100} />

	<!-- Title + Button Container -->
	<div
		class="z-100 mt-48 flex h-full flex-col items-center gap-6 md:mt-0 md:ml-48 md:justify-center"
	>
		<div class="z-100 flex flex-col items-center justify-center gap-2">
			<h1 class="font-beachday text-5xl md:text-6xl lg:text-8xl">SwampHacks XI</h1>
			<h2 class="font-beachday text-3xl md:text-4xl lg:text-5xl">January 23rd - 25th</h2>
			<h3 class="font-beachday text-2xl md:text-3xl lg:text-4xl">Newell Hall</h3>
		</div>

		<!-- Button -->
		<div class="z-100 flex w-full flex-col items-center justify-center gap-4">
			<Link
				href="https://app.swamphacks.com/events/53a94d27-4525-489b-8467-a0412722b313/application"
			>
				<Button className="w-full">Register to Hack</Button>
			</Link>

			<Link
				href="https://app.swamphacks.com/events/53a94d27-4525-489b-8467-a0412722b313/mentor-application"
			>
				<Button className="w-full">Register to Mentor</Button>
			</Link>
		</div>
	</div>

	<div
		class="absolute bottom-0 left-[4%] z-49 origin-bottom-left translate-y-[3px] scale-[0.25] md:left-[16%] md:scale-[0.45]"
	>
		<CenturyTower />
	</div>

	<BushWall />
</section>
