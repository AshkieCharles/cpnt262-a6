<script type="module">
  import Title from "../lib/components/Title.svelte";
  import Event from "../lib/components/Event.svelte";
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
  function colorChange(event) {
    document.getElementById("btn").style.backgroundColor = "blue";
  }

  
</script>
<Title />
<button on:click={() => (showEvent = true)}>Show Event</button>
{#if showEvent}
  <Event on:close={() => (showEvent = false)} />  
{/if}
<slot />


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


<button on:click={colorChange} id="btn">Change color</button>