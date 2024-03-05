<script>
    let pages = [
    {url: "./", title: "Home"},
    {url: "./cv", title: "CV"},
	{url: "./projects", title: "Projects"},
	{url: "./contact", title: "Contact"},
    {url: "https://github.com/ricofio", title: "GitHub"},
    ];
    import { page } from '$app/stores';
</script>

<nav>
	{#each pages as p }
        <a href={ p.url } class:current={ "." + $page.route.id === p.url } target={ p.url.startsWith("http") ? "_blank" : null }>
            { p.title }
        </a>
	{/each}
</nav>

<slot/>
