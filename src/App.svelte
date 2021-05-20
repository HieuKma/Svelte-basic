<script>
	import Modal from './Modal.svelte';
	import AddPerson from './addPerson.svelte';

	let showModal = false;

	let people = [
		{ id: 1, name: 'Nguyen Minh Hieu', color: 'red', age: 22 },
		{ id: 2, name: 'Nguyen Thi Ha', color: 'blue', age: 19 },
		{ id: 3, name: 'Nugyen Ngoc Ha My', color: 'orange', age: 5 },
	]

	let handleClick = (id) => {
		people = people.filter(item => item.id !== id)
	}

	const toggleModal = () => {
		showModal = !showModal;
	}

	const testthoi = (event) => {
		const person = event.detail;
		people = [person, ...people];
		showModal = false;
	}
</script>

<Modal {showModal} on:click={toggleModal}>
	<AddPerson on:testdispatch={testthoi} />
</Modal>

<main>
	<button on:click={toggleModal}>Open modal</button>
	{#each people as person (person.id)}
		<h4>{person.name}</h4>
		{#if person.color === 'red' }
			<p><strong>{person.color}</strong></p>
		{/if}
		<p>{person.age} year old, {person.color} belt</p>
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

	/* h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	} */

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>