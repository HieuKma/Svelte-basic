<script>
	export let name;
	let color = 'black';
	let firstName = 'Hieu';
	let lastName = 'Nguyen';

	$: fullname = `${firstName} ${lastName}`;
	$: {
		console.log(color);
		console.log(fullname);
	}

	const handleChangeColor = () => {
		color = 'blue'
	}

	const handleInput = (event) => {
		color = event.target.value
	}
</script>

<main>
	<p>{fullname} - { color }</p>
	<input type="text" bind:value={firstName} >
	<input type="text" bind:value={lastName} >
	<input type="text" bind:value={color} >
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