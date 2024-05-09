<script>
    export let playerRecentMatches;

</script>

<div class="container">
    {#each playerRecentMatches as p}
        <!-- <span>{p.result.split('')[0]}</span> -->
        <span
            class:positive={p.result === "won"}
            class:negative={p.result === "lost"}
        >
            {p.result.split('')[0]}
        </span>
    {/each}    
</div>

<style>
    .container {
        display: flex;
        /* justify-content: space-around; */
        gap: 2px;
        height: 14px;
    }

    span {
        width: 14px;
        height: 100%;
        border-radius: 50%;
        color: white;
        text-transform: uppercase;
        font-size: 0.5rem;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        text-anchor: middle;
    }

    .positive {
        background-color: hsla(160, 100%, 32%, 0.8);
    }

    .negative {
        background-color:  hsl(10, 100%, 48%, 0.8);
    }    
</style>


