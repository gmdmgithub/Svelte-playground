<script>

import {createEventDispatcher} from 'svelte';

const dispacher = createEventDispatcher();

let player ={
    name: "",
    points: null
}

const onSubmit = (e) =>{
    e.preventDefault();
    dispacher("addplayer", player);
    player = {
        name:"",
        points: null
    };
};

</script>


<form on:submit={onSubmit} class="grid-3">

<input type="text" placeholder="Player name" bind:value={player.name}>
<input type="number" placeholder="Player points" bind:value={player.points}>
<input type="submit" class="btn btn-primary" value="Add player">
</form>