<script>
    let pages = [
    {url: "./", title: "Home"},
    {url: "./cv", title: "CV"},
	{url: "./projects", title: "Projects"},
	{url: "./contact", title: "Contact"},
    {url: "https://github.com/ricofio", title: "GitHub"},
    ];
    import { page } from '$app/stores';
    let colorScheme = "light dark";
    let root = globalThis?.document?.documentElement;
    root?.style.setProperty("color-scheme", colorScheme);
    $: root?.style.setProperty("color-scheme", colorScheme);
    let localStorage = globalThis.localStorage ?? {};
    localStorage.colorScheme = colorScheme;
</script>


<nav>
	{#each pages as p }
        <a href={ p.url } class:current={ "." + $page.route.id === p.url } target={ p.url.startsWith("http") ? "_blank" : null }>
            { p.title }
        </a>
	{/each}
</nav>

<style>
    nav a{
        flex: 1;
        text-decoration: none;
        color: inherit;
        text-align: center;
        padding: 0.5em;
    }

    nav {
        --border-color: oklch(50% 10% 200 / 40%);
        display: flex;
        margin-bottom: 3em;
        border-bottom-width: 1px;
        border-bottom-style: solid;
        /* border-bottom-color: oklch(80% 3% 200); */
        /* border-bottom-color: oklch(50% 10% 200); */
        border-bottom-color: var(--border-color);
    }

    .color-scheme {
        position: absolute;
        top: 1rem;
        right: 2rem;
        font: 80%/1.5 system-ui;

    }

    select {
        font: inherit;
        display: block;
        width: 160%;
        box-sizing: border-box;
        margin-block: 0.3em;
    }
</style>

<slot/>
