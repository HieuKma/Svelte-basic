<script>
	let people = [
		{ id: 1, name: 'Hieu', color: 'red', age: 22 },
		{ id: 2, name: 'dd', color: 'blue', age: 19 },
		{ id: 3, name: 'a', color: 'oorange', age: 5 },
	]

	let handleClick = (id) => {
		people = people.filter(item => item.id !== id)
	}
</script>

<main>
	{#each people as person (person.id)}
		<h4>{person.name}</h4>
		<p>{person.color}</p>
		<button on:click={handleClick(person.id)}>Delete</button>
	{:else}
		<p>There are no people to show...</p>
	{/each}
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