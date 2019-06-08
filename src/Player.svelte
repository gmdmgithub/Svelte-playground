<script>
  export let name;
  export let points
  const addPoint = () => points +=1;
  const removePoint = () => points -=1;
  
</script>

<style>
  h1 {
    color: #530f53;
  }
</style>
  <div class="card">
    <h1>Hello {name}!</h1>
    <h3>{points}</h3>
	<button class="btn" on:click={addPoint}>Add</button>
	<button class="btn btn-dark" on:click={removePoint}>Subtract</button>
	{#if points > 102}
	<br>
	
	<input type="number" bind:value={points}>
	{/if}
  </div>
