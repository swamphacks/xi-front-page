
<script lang="ts">
    export let src = "$lib/assets/Hippodrome.png";
    export let alt = "Button Image";
    function onClickTest() {
        console.log("Button clicked!");
    }
    export let onClick;
</script>

<button onclick={onClick} style="background: none; border: none; padding: 0; cursor: pointer; position: relative; z-index: 40;">
    <img src={src} alt={alt} style="display: block; width: 100%; height: auto;" />
</button>