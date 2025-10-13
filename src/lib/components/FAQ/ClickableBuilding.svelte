
<script lang="ts">
    export let src = "$lib/assets/Hippodrome.png";
    export let alt = "Button Image";
    export let title = "Title"
    export let onClick;
</script>



<div class="flex w-auto items-center justify-center max-w-xl">
    <div
        class="flex justify-center size-full transform gap-2 border-2 border-dashed bg-white p-2 shadow-2xl transition-transform duration-300 group hover:-rotate-1"
        onclick={onClick}
         onkeydown={(event) => {}}
         role="button"
         tabindex="0" 
    >
        
        <div class="relative flex flex-col h-full w-full gap-4 bg-[#E8DCC4] p-6">
            <h3 class="font-beachday text-gray-800 text-3xl text-center">{title}</h3>
            <img src={src} alt={alt} style="display: block; width: 100%; height: auto;" class="opacity-90 group-hover:opacity-100 justify-center" />
        </div>
    </div>
</div>