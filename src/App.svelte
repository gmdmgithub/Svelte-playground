<script>
  import Navbar from './Navbar.svelte';
  import Player from './Player.svelte';

let playersList = [
	{
		name: "Alex Doe",
		points: 23
	},
	{
		name: "Max Johnson",
		points: 65

	},
	{
		name: "Donald Mose",
		points: 76
	}
];

</script>

<style>
</style>
<Navbar />
<div class="container">
{#if playersList.length === 0}
	<p>No players</p>
{:else}
	{#each playersList as player}
		<Player name={player.name} points={player.points} />
	{/each}
{/if}
</div>
