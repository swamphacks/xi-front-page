<script>
    import { onMount } from 'svelte';
    import FifthThird from '$lib/assets/sponsor-logos/fifth-third.svg';
    import Amazon from '$lib/assets/sponsor-logos/amazon.svg';
    import Towerhill from '$lib/assets/sponsor-logos/towerhill-insurance.svg';
    import AwesomeMotive from '$lib/assets/sponsor-logos/awesome-motive.svg';
    import MajorLeagueHacking from '$lib/assets/sponsor-logos/mlh.svg';
    import Github from '$lib/assets/sponsor-logos/github.png';
    import PureButtons from '$lib/assets/sponsor-logos/pure-buttons.svg';
    import LakeImg from '$lib/assets/Lake.svg';
    import UFExperientialLearning from '$lib/assets/sponsor-logos/center-experiential-learning.svg';
    import MorganMorgan from '$lib/assets/sponsor-logos/morgan-and-morgan.svg';
    import Andor from '$lib/assets/sponsor-logos/andor.svg';
    let client = false;

    onMount(() => {
        client = true;
    });

    // Sponsors data with specific grid sizes for desktop:
    // - rect-long: 3 columns × 1 row (long rectangle)
    // - small: 1 column × 1 row (small square)
    // - big-rect: 3 columns × 2 rows (big rectangle)
    // - rect-wide: 3 columns × 1 row (even longer rectangle)
    // - co-host: 6 columns × 2 rows (full width, reserved for Co-Host)
    // logoSize: 'small', 'medium', or 'large' - controls logo image size
    // {
    //      name: 'Awesome Motive',
    //      logo: AwesomeMotive,
    //      url: 'https://awesomemotive.com',
    //      gridSize: 'big-rect'
    //  },
    const sponsors = [

        {
            name: 'Fifth Third Bank',
            logo: FifthThird,
            url: 'https://www.53.com/',
            gridSize: 'rect-long',
            logoSize: 'large'
        },
        {
            name: 'Towerhill Insurance',
            logo: Towerhill,
            url: 'https://www.thig.com/',
            gridSize: 'rect-long',
            logoSize: 'large'
        },
        {
            name: 'GitHub',
            logo: Github,
            url: 'https://github.com/',
            gridSize: 'small'
        },
        {
            name: 'Amazon',
            logo: Amazon,
            url: 'https://www.amazon.com/',
            gridSize: 'small'
        },
        {
            name: 'Pure Buttons',
            logo: PureButtons,
            url: 'https://mlh.link/MLH-PureButtons-hackathons/',
            gridSize: 'small'
        },
        {
            name: 'Major League Hacking',
            logo: MajorLeagueHacking,
            url: 'https://mlh.io/',
            gridSize: 'rect-long'
        },
        {
            name: 'UF Center of Experiential Learning',
            logo: UFExperientialLearning,
            url: 'https://www.eng.ufl.edu/undergraduate/programs-and-partnerships/center-for-experiential-learning/',
            gridSize: 'rect-long'
        },
        {
            name: 'Morgan & Morgan',
            logo: MorganMorgan,
            url: 'https://www.forthepeople.com/',
            gridSize: 'rect-long'
        },
        {
            name: 'Andor',
            logo: Andor,
            url: 'https://andorhealth.com/',
            gridSize: 'rect-long'
        }
    ];
</script>

{#if client}
    <section class="relative my-40 min-h-[420px] w-full md:my-60 lg:my-80 md:min-h-[520px] lg:min-h-[600px]">
        <!-- Lake Background Image - Full Opacity -->
        <div class="absolute inset-0">
            <img
                src={LakeImg}
                alt="Lake Background"
                class="absolute top-1/2 left-1/2 w-[500%] max-w-none -translate-x-1/2 -translate-y-1/2 object-cover md:w-[180%] 2xl:w-[120%]"
            />
        </div>

        <!-- Content Container - Positioned over the lake -->
        <div class="relative mx-auto max-w-[90%] md:max-w-5xl lg:max-w-[70%] 2xl:max-w-[60%] p-4 md:p-10">
            <!-- Title Section -->
            <div class="mb-10 md:mb-20 text-center">
                <h2 class="mb-4 font-beachday text-5xl text-white md:text-6xl lg:text-8xl">Our Sponsors</h2>
                <p class="font-beachday text-sm text-white/90 md:text-3xl">
                    Thank you to our amazing sponsors who make SwampHacks possible!
                </p>
            </div>

            <!-- Sponsors Grid Container - Mixed Sizes -->
            <div class="sponsors-grid">
                {#each sponsors as sponsor, index}
                    <div
                        class="group sponsor-card sponsor-{sponsor.gridSize} gentle-float"
                        style="animation-delay: {index * 0.15}s;"
                    >
                        <a
                            href={sponsor.url}
                            target="_blank"
                            rel="noopener noreferrer"
                            aria-label={sponsor.name}
                            class="relative block h-full"
                        >
                            <div class="sponsor-logo-card">
                                <img
                                    src={sponsor.logo}
                                    alt={sponsor.name}
                                    class="sponsor-logo logo-{sponsor.logoSize || 'medium'}"
                                />
                            </div>
                            <div class="sponsor-tooltip">
                                Visit {sponsor.name}
                            </div>
                        </a>
                    </div>
                {/each}
            </div>
        </div>
    </section>
{/if}

<style>
    @keyframes gentle-float {
        0%,
        100% {
            transform: translateY(0px);
        }
        50% {
            transform: translateY(-8px);
        }
    }

    .gentle-float {
        animation: gentle-float 4s ease-in-out infinite;
    }

    /* Sponsors Grid - Tight, Mixed Layout */
    .sponsors-grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-auto-rows: minmax(70px, auto);
        grid-auto-flow: dense;
        gap: 0.5rem;
        width: 100%;
        max-width: 250px;
        margin: 0 auto;
    }

    @media (min-width: 768px) {
        .sponsors-grid {
            max-width: none;
            grid-template-columns: repeat(6, 1fr);
            grid-auto-rows: 100px;
            gap: 1.5rem;
        }
    }

    @media (min-width: 1024px) {
        .sponsors-grid {
            grid-auto-rows: 150px;
            gap: 1.25rem;
        }
    }

    /* Sponsor Card Base */
    .sponsor-card {
        position: relative;
        height: 100%;
        z-index: 1;
        transition: z-index 0s;
    }

    .sponsor-card:hover {
        z-index: 100;
    }

    /* Grid Spans for Different Sizes - Mobile (3 columns) */
    .sponsor-rect-long {
        grid-column: span 3;
        grid-row: span 1;
    }

    .sponsor-rect-wide {
        grid-column: span 3;
        grid-row: span 1;
    }

    .sponsor-big-rect {
        grid-column: span 3;
        grid-row: span 2;
    }

    .sponsor-small {
        grid-column: span 1;
        grid-row: span 1;
    }

    .sponsor-co-host {
        grid-column: span 3;
        grid-row: span 2;
    }

    /* Desktop (6 columns) */
    @media (min-width: 768px) {
        /* Long rectangle: 3 columns × 1 row */
        .sponsor-rect-long {
            grid-column: span 3;
            grid-row: span 1;
        }

        /* Small squares: 1 column × 1 row */
        .sponsor-small {
            grid-column: span 1;
            grid-row: span 1;
        }

        /* Big rectangle: 3 columns × 2 rows */
        .sponsor-big-rect {
            grid-column: span 3;
            grid-row: span 2;
        }

        /* Even longer rectangle: 3 columns × 1 row */
        .sponsor-rect-wide {
            grid-column: span 3;
            grid-row: span 1;
        }

        /* Co-Host: 6 columns × 2 rows */
        .sponsor-co-host {
            grid-column: span 6;
            grid-row: span 2;
        }
    }

    /* Logo Card Container */
    .sponsor-logo-card {
        display: flex;
        align-items: center;
        justify-content: center;
        min-height: 60px;
        padding: 0.5rem;
        border-radius: 0.5rem;
        transition: all 0.3s ease;
        overflow: hidden;
        background-color: rgba(255, 255, 255, 0.15);
        backdrop-filter: blur(4px);
    }

    /* Different box shadows for different card sizes */
    .sponsor-rect-long .sponsor-logo-card,
    .sponsor-rect-wide .sponsor-logo-card {
        box-shadow: 0 15px 30px -8px rgba(59, 130, 246, 0.6);
    }

    .sponsor-big-rect .sponsor-logo-card {
        box-shadow: 0 20px 40px -10px rgba(59, 130, 246, 0.6);
    }

    .sponsor-small .sponsor-logo-card {
        box-shadow: 0 10px 25px -6px rgba(59, 130, 246, 0.6);
    }

    /* Use height 100% for items that span multiple rows, but not for small items */
    .sponsor-rect-long .sponsor-logo-card,
    .sponsor-rect-wide .sponsor-logo-card,
    .sponsor-big-rect .sponsor-logo-card,
    .sponsor-co-host .sponsor-logo-card {
        height: 100%;
    }

    @media (min-width: 768px) {
        .sponsor-logo-card {
            border-radius: 1rem;
            min-height: 100px;
        }
    }

    /* Different padding for different sizes - Mobile */
    .sponsor-rect-long .sponsor-logo-card {
        padding: 0.4rem;
        min-height: 80px;
        height: auto;
        max-height: 80px;
    }

    .sponsor-big-rect .sponsor-logo-card {
        padding: 0.5rem;
        min-height: 120px;
    }

    .sponsor-co-host .sponsor-logo-card {
        padding: 0.75rem;
        min-height: 140px;
    }

    .sponsor-small .sponsor-logo-card {
        padding: 0.4rem;
        height: 100%;
    }

    @media (min-width: 768px) {
        .sponsor-rect-long .sponsor-logo-card {
            padding: 1rem;
            min-height: 100px;
            height: 100%;
            max-height: none;
        }
        .sponsor-big-rect .sponsor-logo-card {
            padding: 2rem;
            min-height: 200px;
        }

        .sponsor-co-host .sponsor-logo-card {
            padding: 3rem;
            min-height: 300px;
        }

        .sponsor-small .sponsor-logo-card {
            height: 100%;
        }
    }

    /* Logo Image */
    .sponsor-logo {
        height: auto;
        max-width: 80%;
        max-height: 80%;
        padding: 0.25rem;
        object-fit: contain;
    }

    @media (min-width: 768px) {
        .sponsor-logo {
            max-width: 120%;
            max-height: 120%;
            padding: 0.5rem;
        }
    }

    /* Make logos larger in rect-long cards */
    .sponsor-rect-long .sponsor-logo {
        padding: 0.25rem !important;
        max-width: 70%;
        max-height: 70%;
    }

    @media (min-width: 768px) {
        .sponsor-rect-long .sponsor-logo {
            padding: 0.75rem;
            max-width: 100%;
            max-height: 100%;
        }
    }

    /* Logo Size Variations - Reduce container padding for large logos */
    .sponsor-logo-card:has(.logo-large) {
        padding: 0.25rem !important;
    }

    @media (min-width: 768px) {
        .sponsor-logo-card:has(.logo-large) {
            padding: 1rem !important;
        }

        .sponsor-big-rect .sponsor-logo-card:has(.logo-large) {
            padding: 1.25rem !important;
        }

        .sponsor-co-host .sponsor-logo-card:has(.logo-large) {
            padding: 2rem !important;
        }
    }

    .logo-large {
        max-width: 70% !important;
        max-height: 70% !important;
        padding: 0 !important;
        width: auto !important;
        height: auto !important;
    }

    @media (min-width: 768px) {
        .logo-large {
            max-width: 280% !important;
            max-height: 280% !important;
        }
    }

    /* Hover Effects */
    .group:hover .sponsor-logo-card {
        transform: scale(1.05);
    }

    .sponsor-rect-long:hover .sponsor-logo-card,
    .sponsor-rect-wide:hover .sponsor-logo-card {
        box-shadow: 0 25px 50px -10px rgba(59, 130, 246, 0.5);
    }

    .sponsor-big-rect:hover .sponsor-logo-card {
        box-shadow: 0 30px 60px -12px rgba(59, 130, 246, 0.6);
    }

    .sponsor-co-host:hover .sponsor-logo-card {
        box-shadow: 0 35px 70px -15px rgba(59, 130, 246, 0.7);
    }

    .sponsor-small:hover .sponsor-logo-card {
        box-shadow: 0 18px 35px -8px rgba(59, 130, 246, 0.4);
    }

    /* Tooltip Styles */
    .sponsor-tooltip {
        position: absolute;
        bottom: -2.5rem;
        left: 50%;
        transform: translateX(-50%);
        white-space: nowrap;
        border-radius: 0.5rem;
        background-color: rgb(31, 41, 55);
        padding: 0.375rem 0.75rem;
        font-size: 0.75rem;
        color: white;
        opacity: 0;
        transition: opacity 0.3s;
        z-index: 101;
        pointer-events: none;
    }

    @media (min-width: 768px) {
        .sponsor-tooltip {
            bottom: -3rem;
            font-size: 0.875rem;
        }
    }

    .group:hover .sponsor-tooltip {
        opacity: 1;
    }
</style>