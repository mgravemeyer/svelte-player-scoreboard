<script>
	let name = "John Doe";
	let points = 100;
	let showControls = false;
	
	const addPoint = () => (points += 1)
	const removePoint = () => (points -= 1)
	const toggleControls = () => (showControls= !showControls)
</script>

<main>
	<div class="container">
		<div class="card">
			<h1>
				{name}
				<button class="btn btn-sm" on:click={toggleControls}>
					{#if showControls}-{:else}+{/if}
				</button>
			</h1>
			<h3>{points}</h3>
			{#if showControls}
				<button class="btn" on:click={addPoint}>+1</button>
				<button class="btn btn-dark" on:click={removePoint}>-1</button>
				<input type="number" value={points}/>
			{/if}
		</div>
	</div>
</main>

<style>
	h1 {
		color: #204f6e;
	}
</style>