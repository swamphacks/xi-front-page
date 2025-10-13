<script lang="ts">
	export let className = ''; // for additional custom classes
	export let onClick = () => {}; // default empty click handler
</script>

<button
	class={`border-button-border text-button-text hover:bg-button-hover active:border-button-active active:bg-button-active active:text-button-active-text cursor-pointer rounded border-2 border-b-6 bg-button-primary px-4 py-2 font-bold ${className}`}
	on:click={onClick}
>
	<slot />
</button>
