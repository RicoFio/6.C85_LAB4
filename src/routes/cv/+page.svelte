<script>
    /** @type {import('./$types').PageData} */
    export let data;
</script>

<svelte:head>
	<title>Curriculum Vitae</title>
</svelte:head>

<section>
    <header>
        <h1>Riccardo's Curriculum Vitae</h1>
        <img src="images/profile_pic_square.png" class="profile_picture"/>
    </header>
</section>
<div class="cv">
    <section>
        <header>
            <h2>Personal Information</h2>
        </header>
        <p>Name: Riccardo</p>
        <p>Surname: Fiorista</p>
        <p>Address: 1234 Web Developer Street, 12345, Web City, Webland</p>
        <p>Phone: 123-456-7890</p>
        <p>Email: <a href="mailto:fiorista@mit.edu">fiorista@mit.edu</a></p>
    </section>
    <section>
        <header>
            <h2>Education</h2>
        </header>
        <article>
            <p><strong>MIT</strong></p>
            <p>Current GPA: 5.0/5.0</p>
            <p>Master of Science in Transportation (MST)</p>
        </article>
        <article>
            <p><strong>University of Amsterdam</strong></p>
            <p>Grade: 8.3/10 | High Distinction</p>
            <p>Master of Science (MSc) in Data Science</p>
        </article>
        <article>
            <p><strong>University of Education</strong></p>
            <p>Grade: 73/100 | First Class</p>
            <p>Bachelor of Science (BSc Hons.) in Artificial Intelligence and Computer Science</p>
        </article>
    </section>
    <section>
        <header>
            <h2>Work Experience</h2>
        </header>
        <article>
            <p><strong>Continuum Industries</strong></p>
            <p>Software Engineer</p>
        </article>
    </section>
</div>
