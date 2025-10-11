<script lang="ts">
	import { gsap } from 'gsap';
	import { onMount } from 'svelte';
	import Car_Front from '$lib/assets/Car_Front.png';

	let car: HTMLImageElement;
	let path: SVGPathElement;

	let scrollY = $state(0);

	onMount(() => {
		window.addEventListener('scroll', () => {
			console.log('Scrolling, current Y:', window.scrollY);
			scrollY = window.scrollY;
		});

		gsap.registerPlugin(MotionPathPlugin, ScrollTrigger);

		let rotateTo = gsap.quickTo(car, 'rotation');
		let prevDirection = 0;

		gsap.to(car, {
			scrollTrigger: {
				trigger: path,
				start: 'top center',
				end: () => '+=' + path.getBoundingClientRect().height,
				scrub: 0.5,
				markers: true,
				onUpdate: (self) => {
					if (prevDirection !== self.direction) {
						rotateTo(self.direction === 1 ? 0 : -180);
						prevDirection = self.direction;
					}
				}
			},
			immediateRender: true,
			motionPath: {
				path: path,
				align: path,
				alignOrigin: [0.5, 0.5],
				autoRotate: 90
			}
		});
	});
</script>

<div class="relative origin-top scale-250 md:scale-300 lg:scale-400 xl:scale-475">
	<img bind:this={car} src={Car_Front} alt="Front of car" class="absolute w-16 xl:w-24" />
	<svg
		width="449"
		height="797"
		viewBox="0 0 449 797"
		fill="none"
		xmlns="http://www.w3.org/2000/svg"
	>
		<g clip-path="url(#clip0_810_2)">
			<path
				d="M116.06 4.7793C134 52.1593 127.67 79.6693 118.98 95.8893C103.5 124.749 65.6101 115.299 34.3101 153.689C23.7401 166.649 4.57005 212.099 18.2501 244.839C26.8801 265.489 50.38 275.189 56.21 277.379C72.54 283.509 109.21 283.949 121.17 283.609C154.11 282.689 182.97 292.459 202.19 327.269C218.05 355.999 210.23 398.719 186.86 419.099C169.22 434.489 126.73 436.229 100 442.009C73.2701 447.789 20.9001 499.609 16.7901 554.419C10.2201 642.029 36.9601 693.499 86.1301 729.299C165.24 786.899 259.38 782.809 268.61 782.879C359.12 783.609 426.93 753.969 437.95 739.079"
				stroke="#58595B"
				stroke-width="27"
				stroke-miterlimit="10"
			/>
			<path
				d="M115.81 4.23047C133.75 51.6105 127.42 79.1205 118.73 95.3405C103.25 124.2 65.3601 114.75 34.0601 153.14C23.4901 166.1 4.32005 211.55 18.0001 244.29C26.6301 264.94 50.13 274.64 55.96 276.83C72.29 282.96 108.96 283.4 120.92 283.06C153.86 282.14 182.72 291.91 201.94 326.72C217.8 355.45 209.98 398.17 186.61 418.55C168.97 433.94 126.48 435.68 99.7501 441.46C73.0201 447.24 20.6501 499.06 16.5401 553.87C9.97005 641.48 36.7101 692.95 85.8801 728.75C164.99 786.35 259.13 782.261 268.36 782.331C358.87 783.061 426.68 753.421 437.7 738.531"
				stroke="#6D6E71"
				stroke-width="20"
				stroke-miterlimit="10"
			/>
			<path
				d="M116.33 2.40039C117.05 4.31039 117.74 6.19039 118.38 8.04039"
				stroke="#FFD140"
				stroke-width="3"
				stroke-miterlimit="10"
			/>
			<path
				bind:this={path}
				d="M122.03 19.4609C132.64 56.5709 126.85 79.3409 119.26 93.5009C103.78 122.361 65.8898 112.911 34.5898 151.301C24.0198 164.261 4.84984 209.711 18.5298 242.451C27.1598 263.101 50.6598 272.801 56.4898 274.991C72.8198 281.121 109.49 281.561 121.45 281.221C154.39 280.301 183.25 290.071 202.47 324.881C218.33 353.611 210.51 396.331 187.14 416.711C169.5 432.101 127.01 433.841 100.28 439.621C73.2698 445.461 21.1798 497.221 17.0698 552.031C10.4998 639.641 37.2398 691.111 86.4098 726.911C165.52 784.511 259.66 780.421 268.89 780.491C345.42 781.111 405.72 760.011 429.19 744.481"
				stroke="#FFD140"
				stroke-width="3"
				stroke-miterlimit="10"
				stroke-dasharray="11.99 11.99"
			/>
			<path
				d="M434.01 740.951C435.84 739.441 437.25 738.011 438.23 736.701"
				stroke="#FFD140"
				stroke-width="3"
				stroke-miterlimit="10"
			/>
		</g>
		<defs>
			<clipPath id="clip0_810_2">
				<rect width="448.81" height="796.42" fill="white" />
			</clipPath>
		</defs>
	</svg>
</div>
