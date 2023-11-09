<script type="module">
  import { createEventDispatcher } from "svelte";
  

  const eventDispatch = createEventDispatcher()

</script>


<div>
  <h2>
    Hello There
  </h2>
  <button on:click={() => eventDispatch('close')}>Close</button>
</div>

<style>
  div {
    margin-top: 2rem;
  }
  h2 {
    max-width: 11ch;
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