<script lang="ts">
	import Button from '../Button/Button.svelte';
	import Link from '../Link/Link.svelte';
	import BushWall from './BushWall.svelte';
	import CenturyTower from './CenturyTower.svelte';
	import MovingCloud from './MovingCloud.svelte';
	import MovingPlane from './MovingPlane.svelte';
</script>

<section class="relative h-screen w-full overflow-hidden bg-sky-background">
	<MovingPlane duration={30} />

	<!-- Clouds -->
	<MovingCloud variant={1} duration={300} />
	<MovingCloud variant={2} duration={310} />
	<MovingCloud variant={3} duration={280} />
	<MovingCloud variant={4} duration={320} />
	<MovingCloud variant={1} duration={278} />
	<MovingCloud variant={3} duration={293} />

	<!-- Title + Button Container -->
	<div
		class="z-100 mt-48 flex h-full flex-col items-center gap-6 md:mt-0 md:ml-48 md:justify-center"
	>
		<div class="z-100 flex flex-col items-center justify-center gap-2">
			<h1 class="font-beachday text-5xl md:text-6xl lg:text-8xl 2xl:text-9xl">SwampHacks XI</h1>
			<h2 class="font-beachday text-3xl md:text-4xl lg:text-5xl 2xl:text-6xl">
				January 23rd - 25th
			</h2>
			<h3 class="font-beachday text-2xl md:text-3xl lg:text-4xl 2xl:text-5xl">Newell Hall</h3>
		</div>

		<!-- Button -->

		<div class="z-100 flex w-auto flex-col items-stretch justify-center gap-3">
			<Link
				href="https://app.swamphacks.com/events/53a94d27-4525-489b-8467-a0412722b313/application"
			>
				<Button className="font-beachday text-md text-xl 2xl:text-3xl w-full"
					>Register to Hack</Button
				>
			</Link>

			<Link
				href="https://docs.google.com/forms/d/1CXXY-PgU43g_edHMLboSsQl7Cb45lIH0aX8ptTiG23g/viewform?edit_requested=true"
			>
				<Button className="font-beachday text-md text-xl 2xl:text-3xl w-full"
					>Register to Mentor</Button
				>
			</Link>

			<Link href="https://swamphack.notion.site/2813b41de22f804ba106fa4055ad4df5">
				<Button className="font-beachday text-md text-xl 2xl:text-3xl w-full"
					>Register to Judge</Button
				>
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
