<script>
    import Bathouse from "$lib/assets/Bathouse.svg"
    import CSK from "$lib/assets/student-org-logos/CSK.svg"
    import CSU from "$lib/assets/student-org-logos/CSU.svg"
    import DSI from "$lib/assets/student-org-logos/DSI.svg"
    import FES from "$lib/assets/student-org-logos/FES.svg"
    import GatorRobotics from "$lib/assets/student-org-logos/GatorRobotics.svg"
    import IEEE from "$lib/assets/student-org-logos/IEEE.svg"
    import SASE from "$lib/assets/student-org-logos/SASE.svg"
    import SEC from "$lib/assets/student-org-logos/SEC.svg"
    import SPCB from "$lib/assets/student-org-logos/SPCB.svg"
    import Swamplaunch from "$lib/assets/student-org-logos/Swamplaunch.svg"
    import UFEngAmbassadors from "$lib/assets/student-org-logos/UFEngAmbassadors.svg"
    import UFPuppyClub from "$lib/assets/student-org-logos/UFPuppyClub.svg"
    import UFSIT from "$lib/assets/student-org-logos/UFSIT.svg"
    import UNLITTER from "$lib/assets/student-org-logos/UNLITTER.svg"
    import Wicse from "$lib/assets/student-org-logos/Wicse.svg"
</script>

<section class="flex size-full justify-center">
    <div class="flex size-full flex-col gap-8 items-center relative">
        <h2 class="font-beachday text-5xl md:text-6xl text-white text-center">Student Organizations</h2>
        <p class="font-beachday text-xl md:text-2xl text-white text-center">Shoutout to our amazing partners! Check out their websites by clicking on the bats.</p>
        <!-- Bathouse container with organization logos positioned around it -->
        <div class="mt-40 md:mt-0 relative flex items-center justify-center px-8 md:px-16 md:min-h-[1000px]">
            <!-- Bathouse -->
            <img src={Bathouse} alt="Bathouse" class="w-[350px] md:w-[800px] object-contain relative z-10 gentle-bob">
            
            <!-- Student organization logos positioned around the bathouse with varied spacing -->
            <!-- Top row organizations - much higher up -->
            <div class="absolute -top-32 right-40 md:-left-40 md:top-10 group cursor-pointer z-20 hover:rotate-2">
                <a href="https://ufcskickstart.com/" target="_blank" rel="noopener noreferrer" aria-label="CSK" class="block relative">
                    <img src={CSK} alt="CSK" class="w-40 md:w-[260px] opacity-90 transform -rotate-12 hover:opacity-100 transition-opacity turn-left">
                    <div class="absolute bottom-full left-1/2 transform -translate-x-1/2 translate-y-10 mb-2 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        CSK
                    </div>
                </a>
            </div>
            
            <div class="absolute -top-45 -left-2 md:left-40 md:top-0 group cursor-pointer z-20 hover:rotate-2 turn-right">
                <a href="https://ufcsu.org/" target="_blank" rel="noopener noreferrer" aria-label="CSU" class="block relative">
                    <img src={CSU} alt="CSU" class="w-40 md:w-[260px] opacity-90 transform rotate-6 hover:opacity-100 transition-opacity">
                    <div class="absolute bottom-full left-1/2 transform -translate-x-1/2 mb-2 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        CSU
                    </div>
                </a>
            </div>
            
            <div class="absolute -top-48 right-4 md:-right-60 md:top-80 group cursor-pointer z-20 hover:rotate-2 turn-left">
                <a href="https://www.ufdsi.com/" target="_blank" rel="noopener noreferrer" aria-label="DSI" class="block relative">
                    <img src={DSI} alt="DSI" class="w-40 md:w-[300px] opacity-90 transform -rotate-6 hover:opacity-100 transition-opacity">
                    <div class="absolute left-1/2 transform -translate-x-1/2 -translate-y-30 mb-2 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        DSI
                    </div>
                </a>
            </div>
            
            <div class="absolute -top-25 -right-3 md:right-140 md:top-40 group cursor-pointer z-20 hover:rotate-2 turn-right">
                <a href="https://www.gatorfes.org/" target="_blank" rel="noopener noreferrer" aria-label="FES" class="block relative">
                    <img src={FES} alt="FES" class="w-40 md:w-[260px] opacity-90 transform rotate-12 hover:opacity-100 transition-opacity">
                    <div class="absolute bottom-full left-1/2 transform -translate-x-1/2 translate-y-8 mb-2 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        FES
                    </div>
                </a>
            </div>
            
            <!-- Left side organizations - more spread out vertically -->
            <div class="absolute -top-10 -left-5 md:-left-50 md:top-50 group cursor-pointer z-20 hover:rotate-2 turn-left">
                <a href="https://www.instagram.com/gator_battlebots" target="_blank" rel="noopener noreferrer" aria-label="Gator Robotics" class="block relative">
                    <img src={GatorRobotics} alt="Gator Robotics" class="w-45 md:w-[320px] opacity-90 transform rotate-20 hover:opacity-100 transition-opacity">
                    <div class="absolute top-1/2 transform translate-x-1/2 -translate-y-12 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        Gator Robotics
                    </div>
                </a>
            </div>
            
            <div class="absolute top-16 -left-5 md:left-96 md:top-20 group cursor-pointer z-20 hover:rotate-2 turn-right">
                <a href="https://ieee.ece.ufl.edu/" target="_blank" rel="noopener noreferrer" aria-label="IEEE" class="block relative">
                    <img src={IEEE} alt="IEEE" class="w-40 md:w-[260px] opacity-90 transform rotate-10 hover:opacity-100 transition-opacity">
                    <div class="absolute top-1/2 transform translate-x-20 -translate-y-14 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        IEEE
                    </div>
                </a>
            </div>
            
            
            <div class="absolute -bottom-10 left-20 md:left-20 md:bottom-30 group cursor-pointer z-20 hover:rotate-2 turn-right">
                <a href="https://ufsec.org/" target="_blank" rel="noopener noreferrer" aria-label="SEC" class="block relative">
                    <img src={SEC} alt="SEC" class="w-40 md:w-[260px] opacity-90 transform rotate-20 hover:opacity-100 transition-opacity">
                    <div class="absolute transform translate-x-35 -translate-y-40 mr-2 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        SEC
                    </div>
                </a>
            </div>
            
            <!-- Right side organizations - more spread out vertically -->
            <div class="absolute -bottom-42 right-0 md:-right-50 md:bottom-180 group cursor-pointer z-20 hover:rotate-2 turn-left">
                <a href="https://www.spcbatuf.org/" target="_blank" rel="noopener noreferrer" aria-label="SPCB" class="block relative">
                    <img src={SPCB} alt="SPCB" class="w-40 md:w-[300px] opacity-90 transform -rotate-25 hover:opacity-100 transition-opacity">
                    <div class="absolute top-1/2 transform translate-x-10 -translate-y-20 ml-2 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        SPCB
                    </div>
                </a>
            </div>
            
            <div class="absolute top-10 -right-2 md:right-8 md:top-40 group cursor-pointer z-20 hover:rotate-2 turn-right">
                <a href="https://www.swamplaunch.org/" target="_blank" rel="noopener noreferrer" aria-label="Swamplaunch" class="block relative">
                    <img src={Swamplaunch} alt="Swamplaunch" class="w-40 md:w-[260px] opacity-90 transform hover:opacity-100 transition-opacity">
                    <div class="absolute top-1/2 transform -translate-y-12 ml-2 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        Swamplaunch
                    </div>
                </a>
            </div>
            
            <div class="absolute top-44 right-2 md:right-16 md:top-90 group cursor-pointer z-20 hover:rotate-2 turn-left">
                <a href="https://linktr.ee/ufengineeringambassadors/" target="_blank" rel="noopener noreferrer" aria-label="UF Engineering Ambassadors" class="block relative">
                    <img src={UFEngAmbassadors} alt="UF Engineering Ambassadors" class="w-40 md:w-[260px] opacity-90 transform -rotate-30 hover:opacity-100 transition-opacity">
                    <div class="absolute top-1/2 transform -translate-y-12 -translate-x-10 ml-2 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        UF Engineering Ambassadors
                    </div>
                </a>
            </div>
            
            <div class="absolute top-68 right-5 md:-right-10 md:top-130 group cursor-pointer z-20 hover:rotate-2 turn-right">
                <a href="https://linktree.com/floridapuppyclub/" target="_blank" rel="noopener noreferrer" aria-label="UF Puppy Club" class="block relative">
                    <img src={UFPuppyClub} alt="UF Puppy Club" class="w-40 md:w-[260px] opacity-90 transform hover:opacity-100 transition-opacity">
                    <div class="absolute top-1/2 transform -translate-y-12 ml-2 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        UF Puppy Club
                    </div>
                </a>
            </div>
            
            <!-- Bottom organizations - much lower down -->
            <div class="absolute -bottom-28 -left-5 md:-left-40 md:bottom-100 group cursor-pointer z-20 hover:rotate-2 turn-left">
                <a href="https://ufsit.club/" target="_blank" rel="noopener noreferrer" aria-label="UFSIT" class="block relative">
                    <img src={UFSIT} alt="UFSIT" class="w-40 md:w-[260px] opacity-90 transform rotate-12 hover:opacity-100 transition-opacity">
                    <div class="absolute top-full left-1/2 transform -translate-y-40 -translate-x-1/2 mt-2 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        UFSIT
                    </div>
                </a>
            </div>

            <div class="absolute bottom-5 -left-5 md:-left-40 md:bottom-50 group cursor-pointer z-20 hover:rotate-2 turn-left">
                <a href="https://ufsase.com/" target="_blank" rel="noopener noreferrer" aria-label="UFSIT" class="block relative">
                    <img src={SASE} alt="SASE" class="w-40 md:w-[260px] opacity-90 transform hover:opacity-100 transition-opacity">
                    <div class="absolute top-full left-1/2 transform -translate-y-40 -translate-x-1/2 mt-2 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        SASE
                    </div>
                </a>
            </div>
            
            <div class="absolute -bottom-38 right-30 md:right-50 md:bottom-40 group cursor-pointer z-20 hover:rotate-2 turn-right">
                <a href="https://www.unlitter.org/uf" target="_blank" rel="noopener noreferrer" aria-label="UNLITTER" class="block relative">
                    <img src={UNLITTER} alt="UNLITTER" class="w-40 md:w-[260px] opacity-90 transform -rotate-6 hover:opacity-100 transition-opacity">
                    <div class="absolute left-1/2 transform -translate-x-1/2 -translate-y-45 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        UNLITTER
                    </div>
                </a>
            </div>
            
            <div class="absolute -bottom-60 left-24 md:left-32 md:bottom-70 group cursor-pointer z-20 hover:rotate-2 turn-left">
                <a href="https://ufwicse.com/" target="_blank" rel="noopener noreferrer" aria-label="WICSE" class="block relative">
                    <img src={Wicse} alt="WICSE" class="w-50 md:w-[320px] opacity-90 transform rotate-30 hover:opacity-100 transition-opacity">
                    <div class="absolute left-1/2 transform -translate-x-1/2 -translate-y-45 px-2 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap">
                        WICSE
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
		animation: gentle-bob 2s ease-in-out infinite;
	}

	/* Slight turn animations for logos/bats */
	@keyframes turn-left {
		0%, 100% {
			transform: rotate(0deg);
		}
		50% {
			transform: rotate(-2deg);
		}
	}

	@keyframes turn-right {
		0%, 100% {
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