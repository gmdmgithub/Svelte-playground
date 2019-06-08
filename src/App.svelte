<script>
  import Navbar from './Navbar.svelte';
  import Player from './Player.svelte';
  import AddPlayer from './AddPlayer.svelte';

let playersList = [
	{
		name: "Alex Doe",
		points: 23,
		id:1
	},
	{
		name: "Max Johnson",
		points: 65,
		id:2

	},
	{
		name: "Donald Mose",
		points: 76,
		id:3
	}
];

const addPlayer = (e)=>{
	const newPlayer = e.detail;
	const maxId = playersList.reduce((max, player)=>{ return player.id>max?player.id:max},0);
	newPlayer.id = maxId+1;
	playersList = [...playersList, newPlayer]
}

</script>

<style>
</style>
<Navbar />
<div class="container">
<AddPlayer on:addplayer={addPlayer} />
{#if playersList.length === 0}
	<p>No players</p>
{:else}
	{#each playersList as player}
		<Player name={player.name} points={player.points} id={player.id}/>
	{/each}
{/if}
</div>
