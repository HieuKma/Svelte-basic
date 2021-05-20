<script>
	import Header from './components/Header.svelte';
	import Footer from './components/footer.svelte';
	import Tabs from './shared/Tabs.svelte';


	// Tabs
	let items = ['Minh Hieu', 'Nguyen Minh Hieu'];
	let activeItem = 'Minh Hieu';

	const testthoi = (e) => {
		activeItem = e.detail;
	}
</script>

<Header />
<main>
	<Tabs {activeItem} {items} on:tabChange={testthoi} />
	{#if activeItem === 'Minh Hieu'}
		<p>Poll list component goes here</p>
	{:else if  activeItem === 'Nguyen Minh Hieu' }
		<p>new poll form component goes here</p>
	{/if}
</main>
<Footer />

<style>
	main {
		max-width: 960px;
		margin: 40px auto;
	}
</style>