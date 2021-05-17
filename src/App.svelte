<script>
	export let name;
	let ten = 'abc';
	let color = 'black';

	const handleChangeColor = () => {
		color = 'white'
	}
</script>

<main>
	<p>l;isdhfgh;lisj g;</p>
	<h1>Ten tao la:  {ten}</h1>
	<h1>Hello {name}!</h1>
	<p>Màu hiện tại là: { color }</p>
	<button on:click={handleChangeColor}>Change color</button>
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