<script>
    /** @type {import('./$types').PageData} */
	import * as d3 from 'd3';
    export let data;
    import projects from "$lib/projects.json";
    import Projects from "$lib/Projects.svelte";
	import Pie from '$lib/Pie.svelte';
	let selectedYearIndex = -1;

	let query = "";
	let selectedYear;
	$: selectedYear = selectedYearIndex > -1 ? pieData[selectedYearIndex].label : null;

	$: filteredProjects = projects.filter(project => {
		// selectedYearIndex = -1;
		let values = Object.values(project).join("\n").toLowerCase();
		return values.includes(query.toLowerCase());
	});
	$: rolledData = d3.rollups(filteredProjects, v => v.length, d => d.year);
	let pieData
	$: {
		pieData = rolledData.map(([year, count]) => {
			return { value: count, label: year };
		});
		console.log("UEEE", pieData)
	}
	$: filteredByYear = filteredProjects.filter(project => {
		return selectedYear>0 ? project.year === selectedYear : true;
	});

</script>

<svelte:head>
	<title>Projects</title>
</svelte:head>

<h1>{ projects.length } Projects</h1>
<Pie data={pieData} bind:selectedIndex={selectedYearIndex}></Pie>
<input type="search" bind:value={query}
	   aria-label="Search projects" placeholder="🔍 Search projects…" />
<Projects data={filteredByYear}></Projects>
