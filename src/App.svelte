<script>
	export let name;
	let color = 'black';

	const handleChangeColor = () => {
		color = 'blue'
	}

	const handleInput = (event) => {
		color = event.target.value
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p style="color: {color}">Màu hiện tại là: { color }</p>
	<button on:click={handleChangeColor}>Change color</button>
	
	<!-- Cach binh thuong -->
	<!-- <input type="text" on:input={handleInput} value={color}> -->

	<!-- bind 2 chieu -->
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