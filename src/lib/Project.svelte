<script>
    export let info = {};
    export let hLevel = 2;
    let p = info;
</script>

<style>
    article {
        display: grid;
        grid-template-rows: subgrid;
        grid-row: span 4;
        padding: 1em;
    }
</style>

<article>
    <svelte:element this={"h" + hLevel}>{ p.title }</svelte:element>
    <a href={p.link}><img src={p.image} alt={p.alt}></a>
    <p><strong>{ p.year }</strong></p>
    <p>{p.description}</p>
</article>
