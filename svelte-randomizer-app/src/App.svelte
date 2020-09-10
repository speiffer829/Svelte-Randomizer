<script>
import Randomizer from './Randomizer.svelte';
	let list=[];
	let newItem =''

	const addItem = (e) => {
		e.preventDefault();
		if(newItem != ''){
			list.push({item: newItem, id: new Date().getTime()});
			newItem = '';
		}
	}
</script>

<main>
<h1>Randomize Stuff</h1>
<Randomizer list={list}/>
<div class="add-box">
	<form>
		<input type="text" bind:value={newItem} placeholder="Add New Item">
		<button class="btn" type="submit" on:click={addItem}>Add+</button>
	</form>
</div>
<div class="list-box">

	<ul>
		{#each list as item, i (item.id)}
			<li>{i + 1} - d{item.item}</li>
		{/each}
	</ul>
</div>

</main>

