<script lang="ts">
    import Hippodrome from '$lib/assets/Hippodrome.png';
    import ClickableBuliding from './ClickableBuilding.svelte';
    import FAQModal from './FAQModal.svelte';
    let showModal = false;
    function handleClose(){
        showModal = false;
    }
</script>

<div>
    <ClickableBuliding src={Hippodrome} alt="Hippodrome Building" onClick={() => showModal = true} />
    {console.log("check")}
    {#if showModal}
        {console.log("Rendering Modal")}
        <FAQModal onClose={handleClose} />
    {/if}
</div>