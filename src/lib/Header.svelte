<script>
    import { contestData } from '../data/data';

 
    const latestDate = $contestData.map(d => {
        let obj = d;
        obj.date2 = new Date(obj.date)
        return obj;
    }).sort((a, b) => b.date2 - a.date2)[0].date2.toLocaleDateString('en-GB');;    
</script>

<div class="container">
    <p>Dream11 Contest Stats</p>
    <p class="sub-header">IPL 2024 - as on {latestDate}</p>
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        
    }

    p {
        font-size: 2rem;
        /* font-weight: bold;         */
        font-family: "Oswald", sans-serif;
        /* text-transform: uppercase;         */
    }

    .sub-header {
        font-size: 1.2rem;
    }
</style>