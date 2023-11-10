<script type="module">
  import { createEventDispatcher } from "svelte";
  

  const eventDispatch = createEventDispatcher()

</script>


<div>
  <h2>
    Greatest League players the world has to offer.
  </h2>
  <button on:click={() => eventDispatch('close')}>Close</button>
</div>

<style>
  div {
    margin-top: 2rem;
  }
  h2 {
    max-width: 45%;
    display: flex;
    background-color: rgb(0, 0, 0);
    margin: auto;
    margin-bottom: 20px;
    justify-content: center;
    color: white;
  }
  button {
    display: flex;
    margin: auto;
  }
</style>