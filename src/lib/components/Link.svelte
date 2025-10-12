<script lang="ts">
    export let href = ''; // default to empty string
  </script>
  
  <a href={href} target="_blank" rel="noopener noreferrer">
      <slot />
  </a>
  