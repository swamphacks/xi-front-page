<script>
	import Bathouse from '$lib/assets/Bathouse.svg';
	import CSK from '$lib/assets/student-org-logos/CSK.svg';
	import CSU from '$lib/assets/student-org-logos/CSU.svg';
	import DSI from '$lib/assets/student-org-logos/DSI.svg';
	import FES from '$lib/assets/student-org-logos/FES.svg';
	import GatorRobotics from '$lib/assets/student-org-logos/GatorRobotics.svg';
	import IEEE from '$lib/assets/student-org-logos/IEEE.svg';
	import SASE from '$lib/assets/student-org-logos/SASE.svg';
	import SEC from '$lib/assets/student-org-logos/SEC.svg';
	import SPCB from '$lib/assets/student-org-logos/SPCB.svg';
	import Swamplaunch from '$lib/assets/student-org-logos/Swamplaunch.svg';
	import UFEngAmbassadors from '$lib/assets/student-org-logos/UFEngAmbassadors.svg';
	import UFPuppyClub from '$lib/assets/student-org-logos/UFPuppyClub.svg';
	import UFSIT from '$lib/assets/student-org-logos/UFSIT.svg';
	import UNLITTER from '$lib/assets/student-org-logos/UNLITTER.svg';
	import Wicse from '$lib/assets/student-org-logos/Wicse.svg';
	import OSC from '$lib/assets/student-org-logos/OSC.svg';
	import SHPE from '$lib/assets/student-org-logos/SHPE.svg';
	import WingHacks from '$lib/assets/student-org-logos/WingHacks.svg';
</script>

<section class="flex size-full justify-center">
	<div class="relative flex size-full flex-col items-center gap-8">
		<h2 class="text-center font-beachday text-5xl text-white md:text-6xl">Student Organizations</h2>
		<p class="text-center font-beachday text-xl text-white md:text-2xl">
			Shoutout to our amazing partners! Check out their websites by clicking on the bats.
		</p>
		<!-- Bathouse container with organization logos positioned around it -->
		<div
			class="relative mt-40 flex items-center justify-center px-8 md:mt-0 md:min-h-[1000px] md:px-16"
		>
			<!-- Bathouse -->
			<img
				src={Bathouse}
				alt="Bathouse"
				class="gentle-bob relative z-10 w-[350px] object-contain md:w-[800px]"
			/>

			<!-- Student organization logos positioned around the bathouse with varied spacing -->
			<!-- Top row organizations - much higher up -->
			<div
				class="group absolute -top-30 right-50 z-20 cursor-pointer hover:rotate-2 md:-top-5 md:right-10"
			>
				<a
					href="https://ufcskickstart.com/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="CSK"
					class="relative block"
				>
					<img
						src={CSK}
						alt="CSK"
						class="turn-left w-[65px] transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute left-1/2 mb-2 -translate-x-1/2 -translate-y-35 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						CSK
					</div>
				</a>
			</div>

			<div
				class="group turn-right absolute -top-20 -left-2 z-20 cursor-pointer hover:rotate-2 md:top-0 md:left-40"
			>
				<a
					href="https://ufcsu.org/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="CSU"
					class="relative block"
				>
					<img
						src={CSU}
						alt="CSU"
						class="w-[65px] transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute bottom-full left-1/2 mb-2 -translate-x-1/2 translate-y-5 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						CSU
					</div>
				</a>
			</div>

			<div
				class="group turn-left absolute -top-30 right-30 z-20 cursor-pointer hover:rotate-2 md:top-120 md:-right-40"
			>
				<a
					href="https://www.ufdsi.com/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="DSI"
					class="relative block"
				>
					<img
						src={DSI}
						alt="DSI"
						class="w-[65px] transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute left-1/2 mb-2 -translate-x-1/2 -translate-y-30 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						DSI
					</div>
				</a>
			</div>

			<div
				class="group turn-right absolute -top-25 -right-3 z-20 cursor-pointer hover:rotate-2 md:top-40 md:right-200"
			>
				<a
					href="https://www.gatorfes.org/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="FES"
					class="relative block"
				>
					<img
						src={FES}
						alt="FES"
						class="w-[65px] transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute bottom-full left-1/2 mb-2 -translate-x-1/2 translate-y-8 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						FES
					</div>
				</a>
			</div>

			<!-- Left side organizations - more spread out vertically -->
			<div
				class="group turn-left absolute -top-0 left-5 z-20 cursor-pointer hover:rotate-2 md:top-50 md:-left-50"
			>
				<a
					href="https://www.instagram.com/gator_battlebots"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="Gator Robotics"
					class="relative block"
				>
					<img
						src={GatorRobotics}
						alt="Gator Robotics"
						class="w-[65px] -rotate-40 transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute top-1/2 -translate-x-5 -translate-y-18 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						Gator Robotics
					</div>
				</a>
			</div>

			<div
				class="group turn-right absolute -top-20 left-20 z-20 cursor-pointer hover:rotate-2 md:top-0 md:left-96"
			>
				<a
					href="https://ieee.ece.ufl.edu/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="IEEE"
					class="relative block"
				>
					<img
						src={IEEE}
						alt="IEEE"
						class="w-[65px] rotate-10 transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute top-1/2 translate-x-5 -translate-y-20 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						IEEE
					</div>
				</a>
			</div>

			<div
				class="group turn-right absolute -top-20 right-10 z-20 cursor-pointer hover:rotate-2 md:top-10 md:right-40"
			>
				<a
					href="https://ufsec.org/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="SEC"
					class="relative block"
				>
					<img
						src={SEC}
						alt="SEC"
						class="w-[65px] transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute mr-2 translate-x-5 -translate-y-35 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						SEC
					</div>
				</a>
			</div>

			<!-- Right side organizations - more spread out vertically -->
			<div
				class="group turn-left absolute right-0 -bottom-10 z-20 cursor-pointer hover:rotate-2 md:-right-40 md:bottom-140"
			>
				<a
					href="https://www.spcbatuf.org/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="SPCB"
					class="relative block"
				>
					<img
						src={SPCB}
						alt="SPCB"
						class="w-[65px] transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute top-1/2 ml-2 translate-x-10 -translate-y-20 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						SPCB
					</div>
				</a>
			</div>

			<div
				class="group turn-right absolute top-10 -right-2 z-20 cursor-pointer hover:rotate-2 md:top-40 md:right-8"
			>
				<a
					href="https://www.swamplaunch.org/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="Swamplaunch"
					class="relative block"
				>
					<img
						src={Swamplaunch}
						alt="Swamplaunch"
						class="w-[65px] transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute top-1/2 ml-2 -translate-x-10 -translate-y-15 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						Swamplaunch
					</div>
				</a>
			</div>

			<div
				class="group turn-left absolute top-44 right-2 z-20 cursor-pointer hover:rotate-2 md:top-90 md:right-0"
			>
				<a
					href="https://linktr.ee/ufengineeringambassadors/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="UF Engineering Ambassadors"
					class="relative block"
				>
					<img
						src={UFEngAmbassadors}
						alt="UF Engineering Ambassadors"
						class="w-[65px] transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute top-1/2 ml-2 -translate-x-25 -translate-y-12 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						UF Engineering Ambassadors
					</div>
				</a>
			</div>

			<div
				class="group turn-right absolute right-20 bottom-60 z-20 cursor-pointer hover:rotate-2 md:right-5 md:bottom-50"
			>
				<a
					href="https://linktree.com/floridapuppyclub/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="UF Puppy Club"
					class="relative block"
				>
					<img
						src={UFPuppyClub}
						alt="UF Puppy Club"
						class="w-[65px] transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute top-1/2 ml-2 -translate-y-12 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						UF Puppy Club
					</div>
				</a>
			</div>

			<!-- Bottom organizations - much lower down -->
			<div
				class="group turn-left absolute -bottom-10 left-5 z-20 cursor-pointer hover:rotate-2 md:bottom-100 md:-left-40"
			>
				<a
					href="https://ufsit.club/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="UFSIT"
					class="relative block"
				>
					<img
						src={UFSIT}
						alt="UFSIT"
						class="w-[65px] transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute top-full left-1/2 mt-2 -translate-x-1/2 -translate-y-40 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						UFSIT
					</div>
				</a>
			</div>

			<div
				class="group turn-left absolute bottom-20 left-0 z-20 cursor-pointer hover:rotate-2 md:bottom-50 md:-left-40"
			>
				<a
					href="https://ufsase.com/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="UFSIT"
					class="relative block"
				>
					<img
						src={SASE}
						alt="SASE"
						class="w-[65px] transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute top-full left-1/2 mt-2 -translate-x-1/2 -translate-y-40 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						SASE
					</div>
				</a>
			</div>

			<div
				class="group turn-right absolute -bottom-20 left-20 z-20 cursor-pointer hover:rotate-2 md:bottom-40 md:left-20"
			>
				<a
					href="https://www.unlitter.org/uf"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="UNLITTER"
					class="relative block"
				>
					<img
						src={UNLITTER}
						alt="UNLITTER"
						class="w-[65px] transform opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute -translate-x-0 -translate-y-30 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						UNLITTER
					</div>
				</a>
			</div>

			<div
				class="group turn-left absolute top-60 right-20 z-20 cursor-pointer hover:rotate-2 md:top-170 md:right-50"
			>
				<a
					href="https://ufwicse.com/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="WICSE"
					class="relative block"
				>
					<img
						src={Wicse}
						alt="WICSE"
						class="w-[65px] opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute left-1/2 -translate-x-1/2 -translate-y-30 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						WICSE
					</div>
				</a>
			</div>
			<div
				class="group turn-left absolute -bottom-10 left-50 z-20 cursor-pointer hover:rotate-2 md:bottom-40 md:left-80"
			>
				<a
					href="https://ufosc.org/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="WICSE"
					class="relative block"
				>
					<img
						src={OSC}
						alt="OSC"
						class="w-[65px] opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute left-1/2 -translate-x-1/2 -translate-y-30 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						OSC
					</div>
				</a>
			</div>
			<div
				class="group turn-left absolute bottom-5 left-20 z-20 cursor-pointer hover:rotate-2 md:bottom-90 md:-left-10"
			>
				<a
					href="https://www.shpeuf.com/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="WICSE"
					class="relative block"
				>
					<img
						src={SHPE}
						alt="SHPE"
						class="w-[65px] opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute left-1/2 -translate-x-1/2 -translate-y-30 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						SHPE
					</div>
				</a>
			</div>
			<div
				class="group turn-left absolute -top-5 right-40 z-20 cursor-pointer hover:rotate-2 md:top-5 md:-right-40"
			>
				<a
					href="https://www.winghacks.com/"
					target="_blank"
					rel="noopener noreferrer"
					aria-label="WICSE"
					class="relative block"
				>
					<img
						src={WingHacks}
						alt="SHPE"
						class="w-[65px] opacity-90 transition-opacity hover:opacity-100 md:w-[150px]"
					/>
					<div
						class="absolute left-1/2 -translate-x-1/2 -translate-y-30 transform rounded bg-gray-800 px-2 py-1 text-sm whitespace-nowrap text-white opacity-0 transition-opacity group-hover:opacity-100"
					>
						WingHacks
					</div>
				</a>
			</div>
		</div>
	</div>
</section>

<style>
	@keyframes gentle-bob {
		0%,
		100% {
			transform: translateY(0px);
		}
		50% {
			transform: translateY(-10px);
		}
	}

	.gentle-bob {
		animation: gentle-bob 5s ease-in-out infinite;
	}

	/* Slight turn animations for logos/bats */
	@keyframes turn-left {
		0%,
		100% {
			transform: rotate(0deg);
		}
		50% {
			transform: rotate(-2deg);
		}
	}

	@keyframes turn-right {
		0%,
		100% {
			transform: rotate(0deg);
		}
		50% {
			transform: rotate(2deg);
		}
	}

	.turn-left {
		animation: turn-left 5s ease-in-out infinite;
		transform-origin: center;
	}

	.turn-right {
		animation: turn-right 5s ease-in-out infinite;
		transform-origin: center;
	}
</style>
