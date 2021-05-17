<script>
	let people = [
		// { id: 1, name: 'Hieu', color: 'red', age: 22 },
		// { id: 2, name: 'Ha', color: 'blue', age: 19 },
		// { id: 3, name: 'My', color: 'oorange', age: 5 },
	]
</script>

<main>
	<ul>
		{#each people as item  (item.id)}
			<li>
				<h4>{item.name}</h4>
				<p>{item.color}</p>
			</li>
		{:else}
			<p>There are no people to show...</p>
		{/each}
	</ul>
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