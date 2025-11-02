<script lang="ts">
  import Cloud from './Landing/Cloud.svelte';

  export let height: string = '160px';
  export let className: string = '';
  const pattern = [1, 2, 3, 4];
  const variants = Array.from({ length: 10 }, (_, i) => pattern[i % pattern.length]);
</script>

<div class="cloud-divider {className}" style="height: {height};">
  <div class="cloud-row">
    {#each variants as v, i}
      <div class="cloud-wrap cloud-{(i % 4) + 1}" aria-hidden="true">
        <Cloud variant={v} />
      </div>
    {/each}
  </div>
</div>

<style>
  .cloud-divider {
    width: 100%;
    overflow: hidden;
    display: block;
    position: relative;
    z-index: 60;
    margin-bottom: -10rem;
    pointer-events: none;
  }
  .cloud-row {
    display: flex;
    width: calc(100% + 8rem);
    gap: 0;
    align-items: flex-end;
    justify-content: flex-start;
    transform: translateX(-1rem);
  }

  .cloud-wrap {
    flex: 0 0 24%;
    min-width: 18%;
    display: flex;
    align-items: flex-end;
    justify-content: center;
    margin-left: -10%;
    position: relative;
    z-index: 1;
  }

  :global {
    .cloud-wrap > svg {
      width: 100%;
      height: 100%;
      display: block;
    }

    .cloud-1 > svg { transform: scaleX(1.02) translateY(4%); }
    .cloud-2 > svg { transform: scaleX(0.98) translateY(0%); }
    .cloud-3 > svg { transform: scaleX(1.06) translateY(6%); }
    .cloud-4 > svg { transform: scaleX(0.95) translateY(2%); }
  }

  .cloud-wrap:nth-child(odd) { z-index: 2; }
  .cloud-wrap:nth-child(even) { z-index: 1; transform: translateY(6%); }

  @media (max-width: 768px) {
    .cloud-wrap { flex: 0 0 40%; margin-left: -12%; }
  }

  @media (max-width: 640px) {
    :global(.cloud-divider) { height: 100px; }
  }

</style>
