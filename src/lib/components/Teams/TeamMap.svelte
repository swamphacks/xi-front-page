<script lang="ts">
    import { onMount } from 'svelte';
    
    type Player = {
        id: number;
        name: string;
        role: string;
        linkedin: string;
        x: number;
        y: number;
        img: string;
        team: string;
    };

    import Stadium from '$lib/assets/stadium.svg';
    import Alex from '$lib/assets/dot-pfps/alexander-wang.png';
    import Phoenix from '$lib/assets/dot-pfps/phoenix-gutierrez.png';
    import Stanley from '$lib/assets/dot-pfps/stanley-ke.jpg';
    import Hugo from '$lib/assets/dot-pfps/hugo-liu.png';
    import Hieu from '$lib/assets/dot-pfps/hieu-nguyen.png';
    import Kayla from '$lib/assets/dot-pfps/kayla-inoa.png';
    import Anthony from '$lib/assets/dot-pfps/anthony-le.png';
    import Tina from '$lib/assets/dot-pfps/tina-mei.png';
    import MJ from '$lib/assets/dot-pfps/mj-tady.png';
    import Shivani from '$lib/assets/dot-pfps/shivani-chandrasekar.png';
    import Jessie from '$lib/assets/dot-pfps/jessie-lin.png';
    import Zhiting from '$lib/assets/dot-pfps/zhiting-li.png';
    import Jessica from '$lib/assets/dot-pfps/jessica-barnes.png';
    import Daniel from '$lib/assets/dot-pfps/daniel-romero.png';
    import Nikki from '$lib/assets/dot-pfps/nikki-chen.png';
    import Gaby from '$lib/assets/dot-pfps/gaby-smith.png';
    import Domenica from '$lib/assets/dot-pfps/domenica-simbana-mosquera.png';
    import Wilson from '$lib/assets/dot-pfps/wilson-goins.png';
    import Alyssa from '$lib/assets/dot-pfps/alyssa-mann.png';
    import Leyna from '$lib/assets/dot-pfps/leyna-huynh.png';
    import Cara from '$lib/assets/dot-pfps/cara-kulhanjian.png';
    import James from '$lib/assets/dot-pfps/james-fouts.png';
    import Mya from '$lib/assets/dot-pfps/mya-ramsey.png';
    import Meaghan from '$lib/assets/dot-pfps/meaghan-knowles.png';
    import Pranathi from '$lib/assets/dot-pfps/pranathi-madishetty.png';
    import Sebastian from '$lib/assets/dot-pfps/sebastian-garcia.png';
    import Brock from '$lib/assets/dot-pfps/brock-gilman.png';
    import Ana from '$lib/assets/dot-pfps/ana-petrela.png';
    import Neema from '$lib/assets/dot-pfps/neema-owji.png';
    import Shane from '$lib/assets/dot-pfps/shane-downs.jpg';
    import Elle from '$lib/assets/dot-pfps/elle-strauss.jpg';
    import Robert from '$lib/assets/dot-pfps/robert-conde.jpg';

    let players: Player[] = [
        // ===== OPERATIONS (row 1 + part of row 2) =====
        {
            id: 1,
            name: 'Meaghan Knowles',
            role: 'Hacker Experience Coordinator',
            linkedin: 'https://www.linkedin.com/in/meaghan-knowles/',
            x: 1700,
            y: 2000,
            img: Meaghan,
            team: 'Operations'
        },
        {
            id: 2,
            name: 'Pranathi Madishetty',
            role: 'Hacker Experience Coordinator',
            linkedin: 'https://www.linkedin.com/in/pranathi-madishetty-393aab287/',
            x: 2100,
            y: 1800,
            img: Pranathi,
            team: 'Operations'
        },
        {
            id: 3,
            name: 'Ana Petrela',
            role: 'Workshop Coordinator',
            linkedin: 'https://www.linkedin.com/in/ana-petrela-bb8bb8317/',
            x: 2500,
            y: 1600,
            img: Ana,
            team: 'Operations'
        },
        {
            id: 4,
            name: 'Neema Owji',
            role: 'Workshop Coordinator',
            linkedin: 'https://www.linkedin.com/in/neema-owji/',
            x: 2900,
            y: 1400,
            img: Neema,
            team: 'Operations'
        },
        {
            id: 5,
            name: 'Sebastian Garcia',
            role: 'Judging & Awards Coordinator',
            linkedin: 'https://www.linkedin.com/in/sebastian-garcia100/',
            x: 3300,
            y: 1250,
            img: Sebastian,
            team: 'Operations'
        },
        {
            id: 6,
            name: 'Brock Gilman',
            role: 'Social Events Coordinator',
            linkedin: 'https://www.linkedin.com/in/brock-gilman/',
            x: 3680,
            y: 1100,
            img: Brock,
            team: 'Operations'
        },
        {
            id: 7,
            name: 'Jessie Lin',
            role: 'Merch Coordinator',
            linkedin: 'https://www.linkedin.com/',
            x: 1450,
            y: 2400,
            img: Jessie,
            team: 'Operations'
        },

        // ===== TECHNOLOGY (remainder of row 2) =====
        {
            id: 8,
            name: 'Stanley Ke',
            role: 'Discord Moderator',
            linkedin: 'https://www.linkedin.com/in/stanley-ke/',
            x: 1900,
            y: 2400,
            img: Stanley,
            team: 'Technology'
        },
        {
            id: 9,
            name: 'Hugo Liu',
            role: 'Software Engineer',
            linkedin: 'https://www.linkedin.com/in/hugo-liu-dolphin/',
            x: 2300,
            y: 2200,
            img: Hugo,
            team: 'Technology'
        },
        {
            id: 10,
            name: 'Hieu Nguyen',
            role: 'Software Engineer',
            linkedin: 'https://www.linkedin.com/in/hieutnguyendev/',
            x: 2700,
            y: 2000,
            img: Hieu,
            team: 'Technology'
        },
        {
            id: 11,
            name: 'Kayla Inoa',
            role: 'UX/UI Designer',
            linkedin: 'https://www.linkedin.com/in/kayla-inoa/',
            x: 3100,
            y: 1800,
            img: Kayla,
            team: 'Technology'
        },

        // ===== FINANCE (row 3) =====
        {
            id: 12,
            name: 'Jessica Barnes',
            role: 'Food/Vendor Relations Coordinator',
            linkedin: 'https://www.linkedin.com/in/jessica-m-barnes-uflorida/',
            x: 3500,
            y: 1600,
            img: Jessica,
            team: 'Finance'
        },
        {
            id: 13,
            name: 'Daniel Romero',
            role: 'Company Connect Coordinator',
            linkedin: 'https://www.linkedin.com',
            x: 3900,
            y: 1420,
            img: Daniel,
            team: 'Finance'
        },
        {
            id: 14,
            name: 'Nikki Chen',
            role: 'Sponsor Relations Coordinator',
            linkedin: 'https://www.linkedin.com/in/nikki-chen23/',
            x: 2850,
            y: 2350,
            img: Nikki,
            team: 'Finance'
        },
        {
            id: 15,
            name: 'Gaby Smith',
            role: 'Sponsor Relations Coordinator',
            linkedin: 'https://www.linkedin.com/in/gabriella-rose-smith/',
            x: 3250,
            y: 2180,
            img: Gaby,
            team: 'Finance'
        },

        // ===== LOGISTICS (row 4) =====
        {
            id: 16,
            name: 'Leyna Huynh',
            role: 'Judges Coordinator',
            linkedin: 'https://www.linkedin.com/in/leynahuynh1/',
            x: 3650,
            y: 1980,
            img: Leyna,
            team: 'Logistics'
        },
        {
            id: 17,
            name: 'Cara Kulhanjian',
            role: 'Mentor Coordinator',
            linkedin: 'https://www.linkedin.com/in/cara-kulhanjian/',
            x: 4050,
            y: 1780,
            img: Cara,
            team: 'Logistics'
        },
        {
            id: 18,
            name: 'James Fouts',
            role: 'Volunteer Coordinator',
            linkedin: 'https://www.linkedin.com/in/james-fouts-4a2307292/',
            x: 3100,
            y: 2650,
            img: James,
            team: 'Logistics'
        },

        // ===== MARKETING =====
        {
            id: 19,
            name: 'MJ Tady',
            role: 'Content Coordinator',
            linkedin: 'https://www.linkedin.com/in/maria-juliana-tady/',
            x: 3500,
            y: 2500,
            img: MJ,
            team: 'Marketing'
        },
        {
            id: 20,
            name: 'Shivani Chandrasekar',
            role: 'Content Coordinator',
            linkedin: 'https://www.linkedin.com/',
            x: 3900,
            y: 2300,
            img: Shivani,
            team: 'Marketing'
        },
        {
            id: 21,
            name: 'Zhiting Li',
            role: 'Public Relations Coordinator',
            linkedin: 'https://www.linkedin.com/in/zhitingli/',
            x: 4300,
            y: 2100,
            img: Zhiting,
            team: 'Marketing'
        },

        // ===== ORGANIZER & EXECUTIVE (unchanged) =====
        {
            id: 22,
            name: 'Elle Strauss',
            role: 'Co-Organizer (President)',
            linkedin: 'https://www.linkedin.com/in/ellestrauss/',
            x: 4900,
            y: 720,
            img: Elle,
            team: 'Executive'
        },
        {
            id: 23,
            name: 'Robert Conde',
            role: 'Co-Organizer (Vice President)',
            linkedin: 'https://www.linkedin.com/in/rcond/',
            x: 5400,
            y: 750,
            img: Robert,
            team: 'Executive'
        },
        {
            id: 24,
            name: 'Mya Ramsey',
            role: 'Executive of Operations',
            linkedin: 'https://www.linkedin.com/in/mya-ramsey-uf/',
            x: 5900,
            y: 810,
            img: Mya,
            team: 'Executive'
        },
        {
            id: 25,
            name: 'Alexander Wang',
            role: 'Executive of Technology',
            linkedin: 'https://www.linkedin.com/in/alexanderwangy/',
            x: 6400,
            y: 900,
            img: Alex,
            team: 'Executive'
        },
        {
            id: 26,
            name: 'Phoenix Gutierrez',
            role: 'Executive of Technology',
            linkedin: 'https://www.linkedin.com/in/phoenixgutierrez/',
            x: 6900,
            y: 980,
            img: Phoenix,
            team: 'Executive'
        },
        {
            id: 27,
            name: 'Domenica Simbana Mosquera',
            role: 'Executive of Finance',
            linkedin: 'https://www.linkedin.com/in/domenica-simbana/',
            x: 7400,
            y: 1100,
            img: Domenica,
            team: 'Executive'
        },
        {
            id: 28,
            name: 'Wilson Goins',
            role: 'Executive of Finance',
            linkedin: 'https://www.linkedin.com/in/wilson-goins/',
            x: 5100,
            y: 1100,
            img: Wilson,
            team: 'Executive'
        },
        {
            id: 29,
            name: 'Anthony Le',
            role: 'Executive of Marketing',
            linkedin: 'https://www.linkedin.com/in/l-anthony/',
            x: 5600,
            y: 1150,
            img: Anthony,
            team: 'Executive'
        },
        {
            id: 30,
            name: 'Tina Mei',
            role: 'Executive of Marketing',
            linkedin: 'https://www.linkedin.com/in/tmeixyz/',
            x: 6100,
            y: 1220,
            img: Tina,
            team: 'Executive'
        },
        {
            id: 31,
            name: 'Alyssa Mann',
            role: 'Executive of Logistics',
            linkedin: 'https://www.linkedin.com/in/alyssa-m-mann/',
            x: 6600,
            y: 1320,
            img: Alyssa,
            team: 'Executive'
        },
        {
            id: 32,
            name: 'Shane Downs',
            role: 'Senior Advisor',
            linkedin: 'https://www.linkedin.com/in/shanemdowns/',
            x: 7100,
            y: 1450,
            img: Shane,
            team: 'Executive'
        }
    ];

    let selected: Player | null = null;
    let isMobile = true;

    onMount(() => {
        isMobile = window.innerWidth < 768;
        const handleResize = () => {
            isMobile = window.innerWidth < 768;
        };
        window.addEventListener('resize', handleResize);
        return () => window.removeEventListener('resize', handleResize);
    });

    function prevPlayer() {
        if (!selected) return;
        const currentIndex = players.findIndex((p) => p.id === selected!.id);
        const newIndex = (currentIndex - 1 + players.length) % players.length;
        selected = players[newIndex];
    }

    function nextPlayer() {
        if (!selected) return;
        const currentIndex = players.findIndex((p) => p.id === selected!.id);
        const newIndex = (currentIndex + 1) % players.length;
        selected = players[newIndex];
    }

    const teamColors: Record<string, string> = {
        Operations: '#f7c868', // orange
        Logistics: '#984af7', // purple
        Finance: '#4dd662', // green
        Technology: '#89c9fa', // blue
        Marketing: '#c9b628', // gold
        Executive: '#cf99c5' // magenta
    };

    function getTeamColor(team: string): string {
        return teamColors[team] || '#7b9b5b'; // default
    }
</script>

<svg viewBox="0 0 8346 4828" preserveAspectRatio="xMidYMid meet" class="absolute left-1/2 top-0 z-0 h-auto -translate-x-1/2 w-[120%] md:w-[105%]">
    <!-- Stadium background -->
    <image href={Stadium} width="8346" height="4828" />

    <!-- Define all clipping paths in one place -->
    <defs>
        {#each players as p}
            <clipPath id={'clip-' + p.id} clipPathUnits="userSpaceOnUse">
                <circle cx={p.x} cy={p.y} r={selected?.id === p.id ? 230 : 175} />
            </clipPath>
        {/each}
    </defs>

    {#if !isMobile}
    <g transform="translate(1220, 410) scale(0.42)">
        <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 1200 320"
            class="mx-auto h-auto w-[600px] [transform:rotateX(32deg)_rotateY(-30deg)_skewX(0deg)]"
        >
            <!-- Backplate (cartoony sign panel) -->
            <g filter="url(#glow)">
                <rect x="40" y="40" width="1120" height="240" rx="26" fill="#1a1a1a" stroke-width="6" />
                <rect
                    x="50"
                    y="50"
                    width="1100"
                    height="220"
                    rx="15"
                    fill="white"
                    stroke="#7b9b5b"
                    stroke-width="20"
                    opacity="0.9"
                />
            </g>
            <text
                x="50%"
                y="60%"
                text-anchor="middle"
                font-size="110"
                font-weight="900"
                font-family="beachday, Luckiest Guy, Impact, system-ui, sans-serif"
                letter-spacing="3"
                fill="#7b9b5b"
                opacity="0.9"
            >
                SwampHacks Team
            </text>
        </svg>
    </g>
    {/if}

    <!-- Player images as circular pfps -->
    {#each players as p}
        <g
            on:click={() => (selected = p)}
            on:keydown={(e) => (e.key === 'Enter' || e.key === ' ') && (selected = p)}
            tabindex="0"
            class="cursor-pointer transition-all duration-300 hover:scale-110"
            role="button"
            aria-label={`Select ${p.name}`}
            style="transform-box: fill-box; transform-origin: center;"
        >
            <!-- Background -->
            <circle cx={p.x} cy={p.y} r={selected?.id === p.id ? 230 : 175} fill={getTeamColor(p.team)} />

            <!-- Profile image (now correctly clipped) -->
            <image
                href={p.img}
                x={p.x - (selected?.id === p.id ? 220 : 175)}
                y={p.y - (selected?.id === p.id ? 220 : 175)}
                width={selected?.id === p.id ? 450 : 350}
                height={selected?.id === p.id ? 450 : 350}
                clip-path={`url(#clip-${p.id})`}
                preserveAspectRatio="xMidYMid slice"
            />

            <!-- Border -->
            <circle
                cx={p.x}
                cy={p.y}
                r={selected?.id === p.id ? 230 : 175}
                stroke={getTeamColor(p.team)}
                stroke-width="18"
                fill="none"
            />
        </g>
    {/each}
</svg>

<!-- Modal for selected player -->
{#if selected}
    <div
        class="fixed inset-0 z-100 flex items-center justify-center bg-black/20 md:items-end md:justify-end md:p-40"
        on:click={() => (selected = null)}
        on:keydown={(e) => e.key === 'Escape' && (selected = null)}
        role="dialog"
        aria-modal="true"
    >
        <div
            class="animate-fadeIn relative w-[80%] rounded-2xl bg-white p-8 text-center shadow-2xl md:w-[400px]"
            on:click|stopPropagation
            on:keydown|stopPropagation
            role="document"
        >
            <!-- Close button -->
            <button
                type="button"
                class="absolute top-3 right-5 text-2xl text-gray-500 hover:text-black"
                on:click={() => (selected = null)}
                aria-label="Close modal"
            >
                &times;
            </button>

            <!-- Navigation buttons -->
            <button
                type="button"
                class="absolute top-1/2 left-[-40px] flex h-12 w-12 -translate-y-1/2 items-center justify-center rounded-full border-2 border-[#183000] bg-white text-3xl text-black shadow-lg transition duration-100 hover:scale-104 md:left-[-60px]"
                on:click={prevPlayer}
                aria-label="Previous player"
            >
                <svg
                    class="w-8 text-[#183000] md:w-15"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                >
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"
                    ></path>
                </svg>
            </button>

            <button
                type="button"
                class="absolute top-1/2 right-[-40px] flex h-12 w-12 -translate-y-1/2 items-center justify-center rounded-full border-2 border-[#183000] bg-white text-3xl text-black shadow-lg transition duration-100 hover:scale-102 md:right-[-60px]"
                on:click={nextPlayer}
                aria-label="Next player"
            >
                <svg
                    class="w-8 text-[#183000] md:w-15"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                >
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"
                    ></path>
                </svg>
            </button>
            <!-- Team name -->
            <p class="mb-2 font-beachday text-4xl" style="color: {getTeamColor(selected.team)};">
                {selected.team}
            </p>

            <!-- Player image -->
            <img
                src={selected.img}
                alt={selected.name}
                class="mx-auto mb-4 h-40 w-40 rounded-full border-4 object-cover"
                style="border-color: {getTeamColor(selected.team)};"
            />

            <!-- Player name -->
            <h2 class="text-2xl font-semibold">
                {selected.name}
            </h2>

            <!-- Player role -->
            <p class="mt-1 text-lg text-[#183000]">{selected.role}</p>

            <!-- LinkedIn icon link -->
            <a
                href={selected.linkedin}
                target="_blank"
                rel="noopener noreferrer"
                class="mt-3 inline-flex items-center gap-2 text-blue-600 transition hover:text-blue-800"
            >
                <!-- LinkedIn SVG icon -->
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 24 24"
                    fill="currentColor"
                    class="h-6 w-6"
                >
                    <path
                        d="M4.98 3.5C4.98 4.88 3.86 6 2.5 6S0 4.88 0 3.5 1.12 1 2.5 1 4.98 2.12 4.98 3.5zM.5 8h4V24h-4V8zm7.5 0h3.8v2.2h.05c.53-1 1.84-2.2 3.8-2.2 4.06 0 4.8 2.67 4.8 6.15V24h-4v-7.75c0-1.85-.03-4.22-2.57-4.22-2.58 0-2.98 2.01-2.98 4.1V24h-4V8z"
                    />
                </svg>
                <span>LinkedIn</span>
            </a>

            <!-- Player info -->
            <!-- <p class="mt-4 text-gray-600">
                Number: {selected.id}<br />
                More player info can go here.
            </p> -->
        </div>
    </div>
{/if}