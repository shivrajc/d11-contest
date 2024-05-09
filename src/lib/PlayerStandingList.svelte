<script>
    import { playerStats } from '../data/data';
    import { contestData } from '../data/data';
    import PlayerStanding from './PlayerStanding.svelte';


</script>

<div class="container">
    {#each $playerStats as player}
        <PlayerStanding playerData={player} />
    {/each}
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        gap: 20px;
    }
</style>