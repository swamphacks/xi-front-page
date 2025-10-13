
<script lang="ts">
    export let src = "$lib/assets/Hippodrome.png";
    export let alt = "Button Image";
    export let onClick;
	import UFArch from '$lib/assets/uf-arch-building.svg';
	import PostcardSticker from '$lib/assets/sh-postcard-sticker.png';
    import Squiggly from "$lib/assets/squiggly.svg";
    import Airmail from "$lib/assets/air-mail.svg";
</script>



<div class="flex w-[10rem] md:mr-10 md:w-[20rem] lg:w-[30rem] xl:w-[40rem] items-center justify-center">
    <div
        class="flex size-full -rotate-1 transform gap-2 border-2 border-dashed bg-white p-2 shadow-2xl transition-transform duration-300 hover:-rotate-1"
    >

        <div class="relative flex h-full w-full gap-4 bg-[#E8DCC4] p-6">
            <button onclick={onClick} class ="gentle-bob hover:scale-102 opacity-80 hover:opacity-100" style="background: none; border: none; padding: 0; cursor: pointer; position: relative; z-index: 40; ">
                <img src={src} alt={alt} style="display: block; width: 100%; height: auto;" />
            </button>
            <img
                src={Airmail}
                alt="Airmail"
                class="absolute bottom-2 z-3 left-2 w-15 md:w-20 xl:w-34 h-auto -rotate-5 opacity-90"
            />
        </div>
    </div>
</div>