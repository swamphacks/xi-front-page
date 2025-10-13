<script lang="ts">
    import { slide } from 'svelte/transition';
    import { quintOut } from 'svelte/easing';

    const {onClose, title, faqs} = $props();

    let activeIndex: number | null = $state(null);

    function toggle(index: number | null) {
        activeIndex = index;
    }
    function linkifyText(text: string) {
    text = text.replace(
      /([\w.-]+@[\w.-]+\.\w+)/g,
      '<a href="mailto:$1" class="underline": underline>$1</a>'
    );
    text = text.replace("MentorLink", '<a href="https://forms.gle/yiKGESaMMdHbRRTu5" target="_blank" class="underline": underline>Here</a>');
    return text
  }
</script>


<div class="fixed inset-0 z-100 flex items-center justify-center bg-black/50" role="button" tabindex="0"   onkeydown={(event) => {
    if (event.key === 'Escape') {
      onClose();
    }
  }} onclick={(e: any) => e.target === e.currentTarget && onClose()}>
    <div class="relative bg-white p-6 rounded-lg shadow-lg max-w-lg w-full">
        <h1 class="justify-center">{title}</h1>
        <button class="absolute top-2 right-2 text-gray-600 hover:text-gray-800 px-5 py-2.5 text-xl" onclick={() => onClose()}>
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
                <div class="pt-3 pb-6 px-6 bg-white" transition:slide={{ duration: 300, easing: quintOut }}>
                    <p class="text-gray-700 leading-relaxed whitespace-pre-line">{@html linkifyText(faq.answer)}</p>
                </div>
            {/if}
        </div>
    {/each}
    </div>
</div>