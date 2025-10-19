<script lang="ts">
	// You might not need a script tag if it's just an SVG,
	// but it's good practice to keep it if you plan to add interactivity later.
	import Car from '$lib/assets/Car_Front_rotatable.png';
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';
	import { MotionPathPlugin, ScrollTrigger } from 'gsap/all';

	let carEl: HTMLImageElement;
	let path: SVGPathElement;

	let scrollY = $state(0);

	onMount(() => {
		window.addEventListener('scroll', () => {
			scrollY = window.scrollY;
		});

		gsap.registerPlugin(MotionPathPlugin, ScrollTrigger);

		gsap.set(carEl, { opacity: 1 });

		const pathTween = gsap.to(carEl, {
			scrollTrigger: {
				trigger: path,
				start: 'top center',
				end: 'bottom top',
				pin: true,
				pinSpacing: false,
				scrub: true
			},
			immediateRender: true,
			motionPath: {
				path: path,
				align: path,
				alignOrigin: [0.5, 0.5],
				autoRotate: true
			},
			ease: 'none',
			paused: true
		});
	});
</script>

<div
	class="pointer-events-none absolute top-0 left-2/5 flex h-full min-h-[200vh] w-full items-start
           justify-center sm:min-h-[250vh] md:min-h-[200vh] lg:min-h-[150vh] xl:min-h-screen"
>
	<img bind:this={carEl} src={Car} alt="Car" class="absolute h-8 opacity-0 md:h-16 lg:h-20" />
	<svg
		stroke-miterlimit="10"
		style="fill-rule:nonzero;clip-rule:evenodd;stroke-linecap:round;stroke-linejoin:round;"
		version="1.1"
		viewBox="1000 0 1000 2560"
		xml:space="preserve"
		xmlns="http://www.w3.org/2000/svg"
		xmlns:xlink="http://www.w3.org/1999/xlink"
		class="h-auto w-full lg:max-w-xl xl:max-w-2xl"
	>
		<defs />
		<clipPath id="ArtboardFrame">
			<rect height="2560" width="1000" x="1000" y="0" />
		</clipPath>
		<g clip-path="url(#ArtboardFrame)" id="Layer-1">
			<path
				d="M1381.99-114.719C1381.99-114.719 1381.99 1020.16 1381.99 1227.5C1381.99 1434.84 1381.99 2002.49 1381.99 2075.63C1381.99 2148.77 1358.13 2430.21 1676.33 2469.96C1994.53 2509.72 2050.93 2569.72 2039.36 2569.72"
				fill="none"
				opacity="1"
				stroke="#404040"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="102.882"
			/>
			<path
				bind:this={path}
				d="M1381.99-114.719C1381.99-114.719 1381.99 1020.16 1381.99 1227.5C1381.99 1434.84 1381.99 2002.49 1381.99 2075.63C1381.99 2148.77 1358.13 2430.21 1676.33 2469.96C1994.53 2509.72 2050.93 2569.72 2039.36 2569.72"
				fill="none"
				opacity="1"
				stroke="#6a6a6a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="77.4977"
			/>
			<path
				d="M1381.58 0L1381.58 29.7649L1381.58 29.7649"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="7.69238"
			/>
			<path
				d="M1381.58 50.3531L1381.58 76.6991"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 105.011L1381.58 134.003"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 165.729L1381.58 196.655"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 227.871L1381.58 260.076"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 286.943L1381.58 319.148"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 346.584L1381.58 378.789"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 404.423L1381.58 436.628"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 465.236L1381.58 497.441"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 527.486L1381.58 559.692"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 588.636L1381.58 620.841"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 652.156L1381.58 684.361"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 716.887L1381.58 749.092"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 782.448L1381.58 814.653"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 845.354L1381.58 877.559"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 905.437L1381.58 937.642"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 968.939L1381.58 1001.14"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1030.02L1381.58 1062.23"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1094.16L1381.58 1126.36"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1159.99L1381.58 1192.19"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1227.5L1381.58 1259.7"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1298.95L1381.58 1331.16"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1364.21L1381.58 1396.42"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1435.05L1381.58 1467.26"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1508.05L1381.58 1540.25"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1585.92L1381.58 1618.12"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1660L1381.58 1692.2"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1729.75L1381.58 1761.96"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1796.37L1381.58 1828.57"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1862.99L1381.58 1895.19"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 1936.11L1381.58 1968.31"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 2008.14L1381.58 2040.34"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 2069.88L1381.58 2102.09"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1381.58 2135.96L1381.58 2155.28L1381.58 2171.72"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1386.36 2213.62C1386.36 2213.62 1386.4 2225.21 1393.93 2246.68"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1409.95 2290.85C1409.95 2290.85 1412.22 2298.65 1427.1 2325.81"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1447.39 2359.37C1447.39 2359.37 1447.72 2362.59 1471.57 2382.71"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1505.89 2412.21C1505.89 2412.21 1517.4 2420.43 1537.2 2428.81"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1581.46 2450.76C1581.46 2450.76 1603.6 2460 1618.66 2461.33"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1661.84 2469.13L1698.96 2475.64"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1744.72 2482.69L1779.31 2489.79"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1818.16 2497.96L1848.09 2502.15"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
			<path
				d="M1891.17 2513.12L1927.19 2520.63"
				fill="none"
				opacity="1"
				stroke="#ffd42a"
				stroke-linecap="butt"
				stroke-linejoin="round"
				stroke-width="8"
			/>
		</g>
	</svg>
</div>
