<script>
    import {createEventDispatcher} from 'svelte';

    let dispatch = createEventDispatcher();

    let name;
    let beltColour;
    let age;
    let skills = [];

    const handleSubmit = () => {
        const person = {
            name,
            beltColour,
            age,
            skills,
            id: Math.random()
        }
        dispatch('testdispatch', person);
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="number" placeholder="age" bind:value={age}>

    <p>Skill: </p>
    <input type="checkbox" bind:group={skills} value="fighting" />Fighting<br>
    <input type="checkbox" bind:group={skills} value="sneaking" />Sneaking<br>
    <input type="checkbox" bind:group={skills} value="running" />Running<br> 

    <p>Belt colour</p>
    <select bind:value={beltColour}>
        <option value="black">black</option>
        <option value="orange">orange</option>
        <option value="brown">brown</option>
        <option value="white">white</option>
    </select>

    <button>Add person</button>
</form>

<style>

</style>