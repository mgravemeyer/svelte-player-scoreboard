<script>
	import { createEventDispatcher } from 'svelte';
	
	const dispatch = createEventDispatcher();

	export let name;
	export let points;
	let showControls = false;
	
	const addPoint = () => (points += 1)
	const removePoint = () => (points -= 1)
	const toggleControls = () => (showControls= !showControls)
	
	const removePlayer = () => {
		dispatch('removeplayer', name)
	}
</script>

<main>
	<div class="card">
		<h1>
			{name}
			<button class="btn btn-sm" on:click={toggleControls}>
			{#if showControls}-{:else}+{/if}
			</button>
			<button class="btn btn-danger" on:click={removePlayer}>
				Remove
			</button>
		</h1>
		<h3>Points: {points}</h3>
		{#if showControls}
			<button class="btn" on:click={addPoint}>+1</button>
			<button class="btn btn-dark" on:click={removePoint}>-1</button>
			<input type="number" value={points}/>
		{/if}
	</div>
</main>

<style>
	h1 {
		color: #204f6e;
	}
</style>