<script lang="ts">
	import { onMount } from 'svelte';
	import Track1 from '$lib/assets/Track_1.png';
	import Track2 from '$lib/assets/Track_2.png';
	import Track3 from '$lib/assets/Track_3.png';
	import Track4 from '$lib/assets/Track_4.png';
	import Track5 from '$lib/assets/Track_5.png';

	interface Track {
		src: string;
		alt: string;
		title: string;
		description: string;
	}

	let tracks: Track[] = [
		{
			src: Track1,
			alt: 'Overall Prize (General Track)',
			title: 'Overall Prize (General Track)',
			description:
				'All projects are considered for the Overall Prize. The General Track is for any innovative projects that do not necessarily fit under any of the other tracks.'
		},
		{
			src: Track2,
			alt: 'AI/ML Track',
			title: 'AI/ML Track',
			description:
				'Projects that leverage artificial intelligence or machine learning to solve problems, create new experiences, or enhance existing technologies.'
		},
		{
			src: Track3,
			alt: 'Health Tech Track',
			title: 'Health Tech Track',
			description:
				'Innovative solutions aimed at improving healthcare delivery, patient outcomes, or medical research through technology.'
		},
		{
			src: Track4,
			alt: 'Sustainability Track',
			title: 'Sustainability Track',
			description:
				'Projects focused on environmental sustainability, renewable energy, conservation, or addressing climate change through technological innovation.'
		},
		{
			src: Track5,
			alt: 'Social Impact Track',
			title: 'Social Impact Track',
			description:
				'Technological solutions designed to address social issues, improve community well-being, or promote equity and inclusion.'
		}
	];
	let current = 0;

	let isMobile = typeof window !== 'undefined' ? window.innerWidth < 768 : false;

	// 2. Initialise radiusX and radiusY using the isMobile value
	let radiusX = isMobile ? 130 : 300; // horizontal spread
	let radiusY = isMobile ? 70 : 90; // vertical curve


	function getPosition(i: number) {
		const offset = (i - current + tracks.length) % tracks.length;
		let pos = offset;
		if (offset > Math.floor(tracks.length / 2)) pos = offset - tracks.length;

		let x: number;
		let y: number;
		let scale: number;

		if (pos === 0) {
			x = 0;
			y = 0;
			scale = 1.3;
		} else if (Math.abs(pos) === Math.floor(tracks.length / 2)) {
			x = pos * radiusX * 0.2;
			y = -radiusY * 2;
			scale = 0.7;
		} else {
			x = pos * radiusX;
			y = -radiusY;
			scale = 1 - Math.abs(pos) * 0.2;
		}

		const opacity = pos === 0 ? 1 : 0.5;
		const filter = pos === 0 ? 'none' : 'grayscale(0.6) brightness(0.7)';

		return { x, y, scale, opacity, filter };
	}

	// Adjust radiusX/Y for mobile
	function updateRadius() {
		if (window.innerWidth < 768) {
			// Tailwind md breakpoint
			radiusX = 130;
			radiusY = 70;
		} else {
			radiusX = 300;
			radiusY = 90;
		}
	}

	onMount(() => {
		updateRadius();
		window.addEventListener('resize', updateRadius);
		return () => window.removeEventListener('resize', updateRadius);
	});
</script>

<section
	class="relative mt-24 flex min-h-[60vh] flex-col items-center justify-center overflow-hidden mb-24"
>
	<div class="mb-24 flex flex-col items-center justify-center gap-2 md:mb-48">
		<h2 class="font-beachday text-5xl text-white">Tracks</h2>
		<p class="text-md font-beachday text-neutral-200">(Click on each landmark to see more)</p>
	</div>
	<div class="relative flex h-[300px] w-full max-w-[600px] items-center justify-center">
		{#each tracks as track, i (i)}
			{@const pos = getPosition(i)}
			<button
				class="absolute cursor-pointer transition-all duration-500 ease-out"
				style={`
            transform: translate(${pos.x}px, ${pos.y}px) scale(${pos.scale});
            opacity: ${pos.opacity};
            filter: ${pos.filter};
          `}
				on:click={() => {
					current = i;
				}}
				aria-label="Select track {i + 1}"
			>
				<img
					src={track.src}
					alt="track"
					class="h-[150px] w-[150px] object-contain md:h-[250px] md:w-[250px]"
				/>
			</button>
		{/each}
	</div>

	<div class="flex w-full flex-col items-center justify-center">
		<div
			class="duration-300 flex flex-col items-center justify-center rounded-2xl border-8 border-amber-200 bg-amber-100 p-4 text-black transition-all gap-4"
		>
			<h3 class="font-beachday text-3xl text-center">{tracks[current].title}</h3>
			<p class="max-w-xl text-center font-montserrat text-lg">{tracks[current].description}</p>
		</div>
	</div>
</section>
