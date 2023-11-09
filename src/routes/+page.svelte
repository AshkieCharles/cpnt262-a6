<script>
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

</script>

<label for="name">Name: </label>
<input type="text" id="name" placeholder="Name" bind:value={newName}>
<label for="team"></label>
<input type="text" id="team" placeholder="Team Name" bind:value={teamName}>
<input type="button" value="">


  {#each esportsPlayers as {name, team} }
    <p>
      {name} is a player for {team} that is competing for the World Cup for League of Legends
    </p>
  {/each}
  