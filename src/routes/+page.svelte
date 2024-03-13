<script>
    /** @type {import('./$types').PageData} */
    export let data;
    import projects from "$lib/projects.json";
    import Project from "$lib/Project.svelte";
    import Projects from "$lib/Projects.svelte";
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<h1>Welcome to my page</h1>
<p>My name is Riccardo and I am a web developer.</p>
<p>Please see the below kittens to lighten up your day:</p>
<img src="images/kittens.webp" alt="Kittens"/>
<br/>

{#await fetch("https://api.github.com/users/ricofio") }
    <p>Loading...</p>
{:then response}
    {#await response.json()}
        <p>Decoding...</p>
    {:then data}
        <h2>My GitHub Stats</h2>
        <dl>
            <dt>Followers</dt>
            <dd>{ JSON.stringify(data.followers) }</dd>
            <dt>Following</dt>
            <dd>{ JSON.stringify(data.following) }</dd>
            <dt>Nr. of Public Repositories</dt>
            <dd>{ JSON.stringify(data.public_repos) }</dd>
        </dl>
    {:catch error}
        <p class="error">
            Something went wrong: {error.message}
        </p>
    {/await}
{:catch error}
    <p class="error">
        Something went wrong: {error.message}
    </p>
{/await}
<br/>
<p>
    Feel free to contact me if you have any questions or if you would like to 
    work together. The best way to reach me is either through the contact form or 
    through LinkedIn <a href="https://www.linkedin.com/in/riccardo-fiorista/">@riccardo.fiorista</a>
    Lorem ipsum dolor sit amet, consectetur 
    adipiscing elit. Nulla nec purus feugiat, molestie ipsum et, consequat nibh.

</p>
<br/>
<h2>Latest Projects</h2>
<br/>
<Projects {projects} highlight=1></Projects>
