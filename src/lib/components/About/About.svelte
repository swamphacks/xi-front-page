<script>
	import AboutTitle from '$lib/assets/about-us-title.svg';
	import UFArch from '$lib/assets/uf-arch-building.svg';
	import PostcardSticker from '$lib/assets/sh-postcard-sticker.png';
	import SHPlaceholder1 from '$lib/assets/sh-placeholder-1.jpg';
	import SHPlaceholder2 from '$lib/assets/sh-placeholder-2.jpg';
	import SHPlaceholder3 from '$lib/assets/sh-placeholder-3.jpg';
	import Squiggly from '$lib/assets/squiggly.svg';
	import Airmail from '$lib/assets/air-mail.svg';
	import UFArchesTitle from '$lib/assets/uf-arches-title.svg';
	let showModal = false;
	let currentImageIndex = 0;

	// Image carousel data
	const carouselImages = [
		{
			src: SHPlaceholder1,
			alt: 'Placeholder'
		},
		{
			src: SHPlaceholder2,
			alt: 'Placeholder'
		},
		{
			src: SHPlaceholder3,
			alt: 'Placeholder'
		}
	];

	function toggleModal() {
		showModal = !showModal;
	}

	function closeModal() {
		showModal = false;
	}

	function nextImage() {
		currentImageIndex = (currentImageIndex + 1) % carouselImages.length;
	}

	function prevImage() {
		currentImageIndex = currentImageIndex === 0 ? carouselImages.length - 1 : currentImageIndex - 1;
	}
</script>

<div class="mt-16 flex h-full w-full flex-col items-center gap-6 md:ml-24 md:items-start">
	<img
		src={AboutTitle}
		alt="About Us Title"
		class="mt-8 h-auto w-[15rem] max-w-full md:mt-12 md:mr-10 md:w-[18rem] lg:mt-16 lg:w-[30rem] xl:mt-20 xl:w-[40rem]"
	/>
	<div
		class="flex w-[95%] items-center justify-center md:mr-10 md:w-[34rem] lg:w-[44rem] xl:w-[60rem]"
	>
		<div
			class="flex size-full -rotate-1 transform gap-2 border-2 border-dashed bg-white p-2 shadow-2xl transition-transform duration-300 hover:-rotate-1"
		>
			<div class="relative flex h-full w-full gap-4 bg-[#E8DCC4] p-6">
				<!-- Postcard Image/Icon Area -->
				<div
					class="relative mb-3 flex h-full flex-1/2 flex-col items-center justify-center text-7xl"
				>
					<img src={UFArchesTitle} alt="UF Arches Title" />
					<img src={UFArch} on:click={toggleModal} alt="UF Arch Building" class="gentle-bob" />
				</div>

				<!-- Divider -->
				<div class="w-0.5 bg-gray-600"></div>

				<!-- Postcard Content Carousel -->
				<div
					class="z-2 flex h-48 flex-1/2 flex-col items-center justify-center gap-2 font-mono leading-relaxed text-gray-800 md:h-96 md:gap-6 lg:h-[28rem] xl:h-[32rem]"
				>
					<div class="text-sm font-bold md:text-xl lg:text-2xl xl:text-4xl">
						Greetings from SwampHacks!
					</div>
					<!-- Carousel Image -->
					<div class="relative mb-2 flex h-20 items-center justify-center md:h-40 lg:h-48 xl:h-50">
						<img
							src={carouselImages[currentImageIndex].src}
							alt={carouselImages[currentImageIndex].alt}
							class="max-h-full max-w-full border-2 border-dashed object-contain"
						/>
					</div>
					<!-- Navigation Controls -->
					<div class="mb-2 flex items-center justify-center gap-1 md:gap-2">
						<button
							on:click={prevImage}
							class="rounded-full bg-white/80 p-0.5 shadow-sm transition-all duration-200 hover:bg-white md:p-1"
							aria-label="Previous image"
						>
							<svg
								class="h-2 w-2 text-gray-700 md:h-3 md:w-3"
								fill="none"
								stroke="currentColor"
								viewBox="0 0 24 24"
							>
								<path
									stroke-linecap="round"
									stroke-linejoin="round"
									stroke-width="2"
									d="M15 19l-7-7 7-7"
								></path>
							</svg>
						</button>

						<!-- Dots Indicator -->
						<div class="flex gap-0.5 md:gap-1">
							{#each carouselImages as _, index}
								<button
									on:click={() => (currentImageIndex = index)}
									class="h-1.5 w-1.5 rounded-full transition-all duration-200 md:h-2 md:w-2 {currentImageIndex ===
									index
										? 'bg-gray-700'
										: 'bg-gray-300'}"
									aria-label="Go to image {index + 1}"
								></button>
							{/each}
						</div>

						<button
							on:click={nextImage}
							class="rounded-full bg-white/80 p-0.5 shadow-sm transition-all duration-200 hover:bg-white md:p-1"
							aria-label="Next image"
						>
							<svg
								class="h-2 w-2 text-gray-700 md:h-3 md:w-3"
								fill="none"
								stroke="currentColor"
								viewBox="0 0 24 24"
							>
								<path
									stroke-linecap="round"
									stroke-linejoin="round"
									stroke-width="2"
									d="M9 5l7 7-7 7"
								></path>
							</svg>
						</button>
					</div>
					<!-- Carousel Message -->
					<p
						class="text-center text-[8px] leading-3 tracking-tight italic decoration-1 md:text-[14px] md:leading-4 lg:leading-6 xl:text-[20px]"
					>
						Join us for an epic road trip through UF with innovation and nature
					</p>
				</div>
				<!-- Background images -->
				<img
					src={PostcardSticker}
					alt="Postcard Sticker"
					class="absolute -top-2 -right-2 h-auto w-15 md:-top-8 md:-right-6 md:w-20 xl:w-40"
				/>
				<img
					src={Squiggly}
					alt="Squiggly"
					class="absolute bottom-5 left-10 z-2 h-auto w-30 -rotate-2 opacity-90 md:w-50"
				/>
				<img
					src={Airmail}
					alt="Airmail"
					class="absolute bottom-2 left-2 z-3 h-auto w-15 -rotate-5 opacity-90 md:w-20 xl:w-34"
				/>
			</div>
		</div>
	</div>

	<div
		class="mt-6 w-full px-4 font-montserrat text-base leading-relaxed font-medium text-[#F7F2E9] md:mt-12 md:max-w-1/2 md:px-0 md:text-lg lg:text-xl"
	>
		<p class="mb-4">
			SwampHacks is the University of Florida’s flagship hackathon, bringing together <span
				class="font-bold">300+</span
			> students each year for 36 hours of creativity, collaboration, and innovation.
		</p>
		<p class="mb-4">
			Recognized for excellence by <span class="font-bold"
				>UF’s Herbert Wertheim College of Engineering</span
			>, SwampHacks offers hands-on workshops, mentorship, and community-building activities that
			help hackers grow their skills and bring their ideas to life.
		</p>
		<p>
			Whether you’re a first-time hacker or a seasoned coder, SwampHacks is the place to build,
			connect, and inspire.
		</p>
	</div>
</div>

<!-- <div class="absolute -top-2 right-0 w-15 -rotate-5">
				<img src={PostcardSticker} alt="Postcard Sticker" class="w-full" />
			</div> -->

<style>
	@keyframes gentle-bob {
		0%,
		100% {
			transform: translateY(0px);
		}
		50% {
			transform: translateY(-5px);
		}
	}

	.gentle-bob {
		animation: gentle-bob 2s ease-in-out infinite;
	}
</style>
