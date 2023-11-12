<script>
	import Button from '../components/Btn.svelte';
	// slide array to loop through
  // The reason why there is an empty string is because we want to show that the first player is #1 in the world and an empty string at the end to render the last person on the list instead of skipping it.
	const worldPlayers = ['','Faker', 'Deft', 'Smeb', 'Rekkles', 'Uzi', 'Perkz', 'Deft', 'Beryl', "DoubleLift", "Bengi", ''];


	
	// We start on 1
	let playerListIndex = 1;

	// The current players that are being shown to the user.
	let currentSlideContent = worldPlayers[1];

	// We go back 2 of the length to go past the 0 index
	const maxPlayerList = worldPlayers.length - 2;

	// next function
	function nextSlide() {
		if (playerListIndex === maxPlayerList) {
			playerListIndex = 1;
			currentSlideContent = worldPlayers[playerListIndex];
		} else {
			playerListIndex++;
			currentSlideContent = worldPlayers[playerListIndex];
		}
	}

	// previous function
	function previousPlayer() {
		if (playerListIndex === 1) {
			playerListIndex = maxPlayerList;
			currentSlideContent = worldPlayers[playerListIndex];
		} else {
			playerListIndex--;
			currentSlideContent = worldPlayers[playerListIndex];
		}
	}

export let titleWorld = 'Top 10 players for League of Legends'
</script>

<section>
  <h2 class="title">{titleWorld}</h2>
	<h2 class="title">{playerListIndex}: {currentSlideContent}</h2>
	<div>
    <div class="btn"> 
      <Button  text="Previous Player" on:toggle={previousPlayer} />
      <Button  text="Next Player" on:toggle={nextSlide} />
    </div>
	</div>
</section>

<style>
  .title {
    margin: auto;
    margin-top: 2rem;
    text-align: center;
  }
  div {
    margin: auto;
  }
  .btn {
    display: flex;
    justify-content: space-evenly;
    margin-bottom: 2rem;
  }
</style>