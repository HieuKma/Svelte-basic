<script>
	import Header from './components/Header.svelte';
	import Footer from './components/footer.svelte';
	import Tabs from './shared/Tabs.svelte';
	import CreatePollForm from './components/CreatePoll-form.svelte';


	// Tabs
	let items = ['Current Polls', 'Add new Poll'];
	let activeItem = 'Current Polls';

	const testthoi = (e) => {
		activeItem = e.detail;
	}
</script>

<Header />
<main>
	<Tabs {activeItem} {items} on:tabChange={testthoi} />
	{#if activeItem === 'Current Polls'}
		<p>Poll list component goes here</p>
	{:else if  activeItem === 'Add new Poll' }
		<CreatePollForm />
	{/if}
</main>
<Footer />

<style>
	main {
		max-width: 960px;
		margin: 40px auto;
	}
</style>