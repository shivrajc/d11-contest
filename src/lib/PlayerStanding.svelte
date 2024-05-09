<script>
    import { contestData } from '../data/data';
    export let playerData;
    import { format } from "d3";
    import PlayerRecent from './PlayerRecent.svelte';

    const numFormat = format(".0%");
    const numCurrencyFormat = format(".0f")

    const playerContestData = $contestData.filter(d => d.player_id === playerData.player_id).map(d => {
        let obj = d;
        obj.date2 = new Date(obj.date)
        return obj;
    }).sort((a, b) => b.date2 - a.date2);

    const playerRecentMatches = playerContestData.slice(0, playerContestData.length <= 10 ? playerContestData.length : 15)

    
</script>

<div class="container">
    <div class="name-container">
        <!-- <div class="rank">{playerData.rank}</div> -->
        <div class="name"> 
            <span class="value">{playerData.player_name}</span>
            <span class="label">{playerData.player_id}</span>
        </div>
        <div class="profit"> 
            <span class="value" class:negative={playerData.profit<0}  class:positive={playerData.profit>0}>₹{numCurrencyFormat(playerData.profit)}</span>
            <span class="label">PROFIT</span>
        </div>        
   </div>
   <div class="stats-container">
        <div class="stat">
            <span class="stat-label">RANK: </span>            
            <span class="stat-value">{playerData.rank}</span>
        </div>
        <div class="stat">
            <span class="stat-label">PLAYED: </span>            
            <span class="stat-value">{playerData.matches_played}</span>
        </div>
        <div class="stat">
            <span class="stat-label">WON: </span>            
            <span class="stat-value">{playerData.matches_won}</span>
        </div>
        <div class="stat">
            <span class="stat-label">WIN %: </span>            
            <span class="stat-value">{numFormat(playerData.win_rate)}</span>
        </div>
   </div>
   <div class="latest-container">
    <p class="stat-label">LAST 15 MATCHES &RightArrow;</p>
    <PlayerRecent {playerRecentMatches} />
   </div>
</div>

<style>    
    .container {
        padding: 16px;
        /* border-radius: 8px; */
        /* border: 1px solid gray; */
        box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;
        display: flex;
        flex-direction: column;
        gap: 16px;
    }
    .value {
        font-size: 1.2rem;
        color: black;
        font-weight: bold;        
    }


    .label {
        font-size: 0.8rem;
        color: gray;
    }

    .name-container {
        display: flex;
        gap: 12px;
        justify-content: space-between;
    }


    .name, .profit {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        gap: 2px;
    }

    .profit {
        text-align: right;
        align-items: flex-end;
    }
    .positive {
        color: hsl(160, 100%, 32%);
    }

    .negative {
        color:  hsl(10, 100%, 48%);
    }

    .stats-container {
        display: flex;
        gap: 8px;
        justify-content: space-between;
    }

    .stat {
        display: flex;
        gap: 4px;
    }

    .stat-value {
        font-size: 0.7rem;
        color: black;
        font-weight: bold;        
    }


    .stat-label {
        font-size: 0.7rem;
        color: gray;
    }    

    .latest-container {
        display: flex;
        flex-direction: column;
        gap:4px
    }
</style>