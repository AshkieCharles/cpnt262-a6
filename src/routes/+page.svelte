<script type="module">
  import Title from "../lib/components/Title.svelte";
  import Players from '../lib/components/Players.svelte';
  import "../main.css"
  let showEvent = false
  let esportsPlayers = [
    {name: 'Faker', team: "T1"},
    {name: 'Beryl', team: "DRX"},
    {name: 'Deft', team: "Dplus Kia"}
  ]
  let newName
  let teamName

  function newPlayerTeam(event) {
    esportsPlayers = [...esportsPlayers,{name:newName, team:teamName}]
  } 
  function darkMode(event) {
    document.getElementById("inside").style.backgroundColor = "black";
    document.getElementById("inside").style.color = "white";
  }

  function lightMode(event) {
    document.getElementById("inside").style.backgroundColor = "white";
    document.getElementById("inside").style.color = "black";
  }


  
</script>
<main id="inside">

<Players />





<label for="name">Name: </label>
<input type="text" id="name" placeholder="Name" bind:value={newName}>
<label for="team">Team Name: </label>
<input type="text" id="team" placeholder="Team Name" bind:value={teamName}>
<button on:click={newPlayerTeam}>Add New Player</button>


<Title />

  {#each esportsPlayers as {name, team} }
    <p>
      {name} is a player for {team} that is competing for the World Cup for League of Legends
    </p>
  {/each}


<button on:click={darkMode}>Dark Mode</button>
<button on:click={lightMode}>Light Mode</button>
</main>

