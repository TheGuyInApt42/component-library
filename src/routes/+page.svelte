<script>
    import SimpleFooter from "../lib/components/simple-footer/SimpleFooter.svelte";
    import SimpleTabs from "../lib/components/simple-tabs/SimpleTabs.svelte";
    import ContactFooter from "../lib/components/contact-footer/ContactFooter.svelte";
    let address = `<p>343 S 2nd Ave</p>
                    <p>Mount Vernon, NY 10550</p>            
                    <a href="tel:9144194033">Tel: (914)419-4033</a>`

    let hours = `<p>Mon. 	11:30am – 2:45pm & 5pm – 10pm</p>
        <p>Tue. 	11:30am – 2:45pm & 5pm – 10pm</p>
            <p>Wed. 	11:30am – 2:45pm & 5pm – 10pm</p>
                <p>Thu. 	11:30am – 2:45pm & 5pm – 10pm</p>
                    <p>Fri. 	11:30am – 2:45pm & 5pm – 10pm</p>
                        <p>Sat. 	12pm – 10pm</p>
                            <p>Sun. 	12pm – 10pm</p>

                                <p>Holidays:   11:30am – 10pm</p>`
</script>

<h1 class="text-3xl">Welcome to your library project</h1>
<p>Create your package using @sveltejs/package and preview/showcase your work with SvelteKit</p>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<SimpleTabs />

<div class="bg-white">
    space
</div>

<SimpleFooter />

<ContactFooter address={address} hours={hours}/>

