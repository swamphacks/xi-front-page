<script>
	import AboutTitle from '$lib/assets/about-us-title.svg';
	import UFArch from '$lib/assets/uf-arch-building.svg';
	import PostcardSticker from '$lib/assets/sh-postcard-sticker.png';
	import SHPlaceholder from '$lib/assets/sh-placeholder-1.png';
	import Squiggly from '$lib/assets/squiggly.svg';
	import Airmail from '$lib/assets/air-mail.svg';
	import UFArchesTitle from '$lib/assets/uf-arches-title.svg';
	let showModal = false;
	let currentImageIndex = 0;

	// Image carousel data
	const carouselImages = [
		{
			src: SHPlaceholder,
			alt: 'Placeholder'
		},
		{
			src: SHPlaceholder,
			alt: 'Placeholder'
		},
		{
			src: SHPlaceholder,
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
					<img
						src={UFArch}
						on:click={toggleModal}
						alt="UF Arch Building"
						class="gentle-bob opacity-80 hover:scale-102 hover:opacity-100"
					/>
					<!-- Magnifying Glass Icon -->
					<button
						aria-label="View larger image"
						on:click={toggleModal}
						class="absolute top-1/3 right-10 z-10 rounded-full bg-white/80 p-2 shadow-lg transition-all duration-200 hover:scale-110 hover:bg-white"
					>
						<svg
							class="h-4 w-4 text-gray-700"
							fill="none"
							stroke="currentColor"
							viewBox="0 0 24 24"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0zM10 7v3m0 0v3m0-3h3m-3 0H7"
							></path>
						</svg>
					</button>
				</div>

				<!-- Divider -->
				<div class="w-0.5 bg-gray-600"></div>

				<!-- Postcard Content Carousel -->
				<div
					class="z-2 flex h-48 flex-1/2 flex-col items-center justify-center gap-2 md:gap-6 font-mono leading-relaxed text-gray-800 md:h-96 lg:h-[28rem] xl:h-[32rem]"
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
					class="absolute -top-2 -right-2 md:-top-8 md:-right-6 h-auto w-15 md:w-20 xl:w-40"
				/>
				<img
					src={Squiggly}
					alt="Squiggly"
					class="absolute bottom-5 left-10 z-2 h-auto w-30 md:w-50 -rotate-2 opacity-90"
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
		class="mt-6 md:mt-12 w-full px-4 font-montserrat text-base leading-relaxed font-medium text-[#F7F2E9] md:max-w-1/2 md:px-0 md:text-lg lg:text-xl"
	>
		<p class="mb-4">
			SwampHacks is the University of Florida’s flagship hackathon, bringing together <span class="font-bold">300+</span> students
			each year for 36 hours of creativity, collaboration, and innovation.
		</p>
		<p class="mb-4">
			Recognized for excellence by <span class="font-bold">UF’s Herbert Wertheim College of Engineering</span>, SwampHacks offers
			hands-on workshops, mentorship, and community-building activities that help hackers grow their
			skills and bring their ideas to life.
		</p>
		<p>
			Whether you’re a first-time hacker or a seasoned coder, SwampHacks is the place to build,
			connect, and inspire.
		</p>
	</div>
</div>

<!-- Modal -->
{#if showModal}
	<div
		class="fixed inset-0 z-50 flex items-center justify-center bg-black/50 p-4"
		on:click={closeModal}
		on:keydown={(e) => e.key === 'Escape' && closeModal()}
		role="button"
		tabindex="0"
		aria-label="Close modal"
	>
		<div
			class="max-h-[90vh] max-w-4xl overflow-hidden rounded-lg bg-white shadow-2xl"
			on:click|stopPropagation
		>
			<!-- Modal Header -->
			<div class="flex items-center justify-between border-b p-4">
				<h3 class="text-lg font-semibold">Checkpoint 1: UF Arch Building</h3>
				<button on:click={closeModal} class="text-gray-500 transition-colors hover:text-gray-700">
					<svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M6 18L18 6M6 6l12 12"
						></path>
					</svg>
				</button>
			</div>

			<!-- Modal Content -->
			<div class="p-4">
				<img
					src={UFArch}
					alt="UF Arch Building - Full View"
					class="h-auto max-h-[60vh] w-full object-contain"
				/>
				<p class="mt-4 text-sm text-gray-600">
					The iconic UF Arch Building - a symbol of innovation and excellence at the University of
					Florida.
				</p>
			</div>
		</div>
	</div>
{/if}

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
			transform: translateY(-2.5px);
		}
	}

	.gentle-bob {
		animation: gentle-bob 2s ease-in-out infinite;
	}
</style>
