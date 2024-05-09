<script>
    import Ban from "./Ban.svelte";
    import { playerStats } from '../data/data';
    import { contestData } from '../data/data';

    const totalMatchesPlayed = $contestData.filter(d => d.player_id === "FieryFights11").length;
    const totalEntryFee = $playerStats.map(d => d.entry_fee).reduce((accumulator, current) => {
                            return accumulator + current;
                            })
    const totalD11Cut = $playerStats.map(d => d.entry_fee).reduce((accumulator, current) => {
                            return accumulator + current;
                            }) - $playerStats.map(d => d.winnings).reduce((accumulator, current) => {
                            return accumulator + current;
                            })                             
</script>

<div class="ban-list">
    <Ban value={totalMatchesPlayed} label={"Matches"} />
    <Ban value={totalEntryFee} label={"Entry Fee"} isCurrency={true} />
    <Ban value={totalD11Cut} label={"Dream11 Cut"} isCurrency={true}/>
</div>

<style>
    .ban-list {
        display: flex;
        gap: 40px;
    }
</style>

