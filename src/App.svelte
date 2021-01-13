<script>
	// export let name;
	let toDos = [];
	let inputText = "";
	function handleClick() {
		toDos = [...toDos, inputText];
		inputText = "";
		console.log(toDos);
	}
	function completeTask() {}
</script>

<main>
	<h1>ToDo App!</h1>
	<h5>toDo List is: {inputText}</h5>
	<input type="text" bind:value={inputText} />
	<button on:click={handleClick}> Add </button>
	<div>
		{#each toDos as toDo}
			<ul>
				<li on:click={completeTask}>
					{toDo}
				</li>
			</ul>
		{/each}
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

</style>
