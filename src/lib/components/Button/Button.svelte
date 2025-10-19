<script lang="ts">
	export let className = ''; // for additional custom classes
	export let onClick = () => {}; // default empty click handler
</script>

<button
	class="{`border-button-border ${className}`} cursor-pointer rounded border-2 border-b-6 bg-button px-4 py-2 font-bold text-button-text hover:bg-button-hover active:border-button-active active:bg-button-active active:text-button-active-text"
	on:click="{onClick}"
>
	<slot />
</button>
