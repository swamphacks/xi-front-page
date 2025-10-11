<script lang="ts">
    const {onClose} = $props();
    import { slide } from 'svelte/transition';
    import { quintOut } from 'svelte/easing';
    const faqs = [
        {
            question: 'What is Svelte?',
            answer: 'Svelte is a radical new approach to building user interfaces...'
        },
        {
            question: 'How is Svelte different from React or Vue?',
            answer: 'Svelte has no virtual DOM...'
        },
        {
            question: 'Do I need to learn a new syntax?',
            answer: 'Not really! Svelte is mostly HTML, CSS, and JavaScript...'
        }
    ];
    let activeIndex: number | null = $state(null);

    function toggle(index: number | null) {
        activeIndex = index;
    }
</script>

<div class="fixed inset-0 z-100 flex items-center justify-center bg-black/50">
    <div class="relative bg-white p-6 rounded-lg shadow-lg max-w-lg w-full">
        <button class="absolute top-2 right-2 text-gray-600 hover:text-gray-800" onclick={onClose}>
            &times;
        </button>
        {#each faqs as faq, index}
        <div class="border-b border-gray-200 last:border-b-0">
            <button
                class="w-full p-4 flex justify-between items-center bg-gray-50 hover:bg-gray-100 text-left font-semibold cursor-pointer focus:outline-none"
                onclick={() => {if (activeIndex !== index){toggle(index)} else toggle(null)}}
            >
                <span>{faq.question}</span>
                <span
                    class="transform transition-transform duration-300"
                    class:rotate-180={activeIndex === index}
                >
                    ▼
                </span>
            </button>

            {#if activeIndex === index}
                <div class="p-6 bg-white" transition:slide={{ duration: 300, easing: quintOut }}>
                    <p class="text-gray-700 leading-relaxed">{faq.answer}</p>
                </div>
            {/if}
        </div>
    {/each}
    </div>
</div>