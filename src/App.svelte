<script>
	import Header from './components/Header.svelte';
	import Footer from './components/footer.svelte';
	import Tabs from './shared/Tabs.svelte';
	import CreatePollForm from './components/CreatePoll-form.svelte';
	import PollList from './components/PollList.svelte';


	// Tabs
	let items = ['Current Polls', 'Add new Poll'];
	let activeItem = 'Current Polls';

	const testthoi = (e) => {
		activeItem = e.detail;
	}

	let polls = [
		{ 
			id: 1, 
			question: 'Typescript or Javascript ?',
			answerA: 'TS',
			answerB: 'JS',
			votesA: 9,
			votesB: 15
		}
	]

	const handleAdd = (e) => {
		const poll = e.detail;
		polls = [poll, ...polls];
		activeItem = 'Current Polls';
	}
</script>

<Header />
<main>
	<Tabs {activeItem} {items} on:tabChange={testthoi} />
	{#if activeItem === 'Current Polls'}
		<PollList {polls} />
	{:else if  activeItem === 'Add new Poll' }
		<CreatePollForm on:addPoll={handleAdd} />
	{/if}
</main>
<Footer />

<style>
	main {
		max-width: 960px;
		margin: 40px auto;
	}
</style>