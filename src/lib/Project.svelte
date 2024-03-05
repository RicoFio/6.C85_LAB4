<script>
    export let info = {};
    export let hLevel = 2;
    let p = info;
</script>


<article>
    <svelte:element this={"h" + hLevel}>{ p.title }</svelte:element>
    <a href={p.link}><img src={p.image} alt={p.alt}></a>
    <p>{p.description}</p>
</article>
