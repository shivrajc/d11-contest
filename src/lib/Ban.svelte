<script>
    export let value;
    export let label;
    export let isCurrency = false;
</script>

<div class="ban-container">
    <div class="ban-value-container">        
        <span class="ban-value-prefix">{isCurrency ? "₹" : ""}</span>
        <span class="ban-value">{value}</span>
    </div>
    <p class="ban-label">{label}</p>
</div>

<style>
    .ban-container {
        display: flex;
        flex-direction: column;
        gap: 0px;        
        justify-content: flex-start;
        align-items: center;
        font-family: "Oswald", sans-serif;
        text-align: center;        
    }

    .ban-value-container {
        display: flex;
        position: relative;
        gap: 4px;
    }

    .ban-value-prefix {
        font-size: 1.4rem;
        /* font-weight: bold; */
        position: relative;
        top: 6px; 
    }

    .ban-value {
        font-size: 2rem;
        color: black;       
        font-weight: bold; 
    }

    .ban-label {
        font-size: 0.9rem;
        color: gray; 
        text-transform: uppercase;     
        font-weight: 600;  
        letter-spacing: 0.6px;
        text-align: left;
    }
</style>