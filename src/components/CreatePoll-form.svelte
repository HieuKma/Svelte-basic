<script>
    import Button from "../shared/Button.svelte";

    let field = {
        question: '',
        answerA: '',
        answerB: ''
    }

    const submitHandeler = () => {
        console.log(field)
    }
</script>

<form on:submit|preventDefault={submitHandeler}>
    <div class="form-field">
        <label for="question">Poll Question: </label>
        <input type="text" id="question" bind:value={field.question}>
    </div>
    <div class="form-field">
        <label for="answer-a">Answer A: </label>
        <input type="text" id="answer-a" bind:value={field.answerA}>
    </div>
    <div class="form-field">
        <label for="answer-b">Answer B: </label>
        <input type="text" id="answer-b" bind:value={field.answerB}>
    </div>
    <Button type='secondary' flat={true} inverse={true}>Add Poll</Button>
</form>

<style>
    form {
        width: 480px;
        margin: 0 auto;
        text-align: center;
    }
    .form-field {
        margin: 18px auto;
    }
    input {
        width: 100%;
        border-radius: 6px;
    }
    label {
        margin: 10px auto;
        text-align: left;
    }
</style>