<script>
    let name;
    let beltColour;
    let age;
    // let fighting = false;
    // let sneaking = false;
    // let running = false;
    let skills = [];

    const handleSubmit = (e) => {
        e.preventDefault();
        console.log(name, beltColour, age, skills)
    }
</script>

<form on:submit={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="number" placeholder="age" bind:value={age}>

    <p>Skill: </p>
    <!-- <input type="checkbox" bind:checked={fighting} />Fighting<br>
    <input type="checkbox" bind:checked={sneaking} />Sneaking<br>
    <input type="checkbox" bind:checked={running} />Running<br> -->

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