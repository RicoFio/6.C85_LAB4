<script>
    /** @type {import('./$types').PageData} */
    export let data;
</script>

<svelte:head>
	<title>Contact me</title>
</svelte:head>

<h1>Contact me!</h1>
<form action="mailto:fiorista@mit.edu" method="POST" enctype="text/plain">
    <label for="email">Email:</label>
    <input type="email">
    <label for="text">Subject:</label>
    <input type="text">
    <label for="">Message:</label>
    <textarea name="body"></textarea>
    <button>Submit</button>
</form>
