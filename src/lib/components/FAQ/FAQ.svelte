<script lang="ts">
    import Hippodrome from '$lib/assets/Hippodrome.png';
    import ClickableBuliding from './ClickableBuilding.svelte';
    import FAQModal from './FAQModal.svelte';

    let showModal = $state(false);
    let modalTitle: string = $state("state");
    let modalFaqs: any[] = $state([]);

    function handleClose(){ 
        showModal = false;
    }

    function handleOpen(title: string, faqs: any[]){
        modalTitle = title;
        modalFaqs = faqs;
        showModal = true;  
    }

    $effect(() => {
        // This code only runs in the browser when `showModal` changes.
        if (showModal) {
            document.body.classList.add('modal-open');
        }

        // The cleanup function automatically removes the class when the modal closes.
        return () => {
            document.body.classList.remove('modal-open');
        };
    });

    // One of the FAQ Categories, associated with the Hippodrome building
    let generalTitle = "General"
    let generalFaqs = [
        {
            question: 'Hippodrome!',
            answer: 'Balls'
        }
    ];

</script>

<div>
    <ClickableBuliding src={Hippodrome} alt="Hippodrome Building" onClick={() => handleOpen(generalTitle, generalFaqs)}/>
    
    {#if showModal}
        <FAQModal onClose={handleClose} title ={modalTitle} faqs= {modalFaqs} />
    {/if}
</div>