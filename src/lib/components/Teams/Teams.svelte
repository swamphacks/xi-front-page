<script>
    import Stadium from '$lib/assets/stadium.svg';
    import TeamMap from './TeamMap.svelte';
</script>

<div class="relative flex flex-col pb-0">
    <h2 class="relative z-10 mb-10 pt-4 text-center font-beachday text-5xl text-white md:text-7xl">Meet the team!</h2>
    <!-- Team Members Here -->
    <div class="relative team-stadium-container min-h-[200px]" style="height: calc(120vw * 4828 / 8346);">
        <TeamMap />
    </div>
</div>

<style>
    @media (min-width: 768px) {
        .team-stadium-container {
            height: calc(105vw * 4828 / 8346) !important;
            max-height: 1500px;
        }
    }
</style>
