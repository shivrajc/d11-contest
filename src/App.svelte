<script>
  // import svelteLogo from './assets/svelte.svg'
  // import viteLogo from '/vite.svg'
  import { playerStats } from './data/data'
  import BanList from './lib/BanList.svelte';
  import Header from './lib/Header.svelte';
  import PlayerStandingList from './lib/PlayerStandingList.svelte';

  // console.log($playerStats)
</script>

<main>  
  <div class="header">

    <Header />
  </div>
  <div class="container">
    <div class="ban-list">
      <BanList />  
    </div>
    <div class="player-list">
      <PlayerStandingList />
    </div>
  </div>
</main>

<style>
  main {
    max-width: 400px;
    border: 1px solid;
    background-color: var(--red);
    padding: none;
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .header {
    height: 100px;
    padding: 20px;
    color: white;
  }
  .container {
    background-color: white;
    /* border-radius: 12px 12px 0 0; */    
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .ban-list {
    padding: 20px;
    border-bottom: 1px solid var(--red);
  }

  .player-list {
    padding: 0 20px 20px 20px;
  }
</style>
