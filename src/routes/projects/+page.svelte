<script>
    /** @type {import('./$types').PageData} */
    export let data;
    import projects from "$lib/projects.json";
    import Projects from "$lib/Projects.svelte";
</script>

<svelte:head>
	<title>Projects</title>
</svelte:head>

<h1>{ projects.length } Projects</h1>
<Projects {projects}></Projects>
