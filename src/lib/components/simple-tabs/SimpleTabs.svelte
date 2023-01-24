<script>
    // Exports
    export let title = "Menu";
    export let darkMode = false;
    export let darkModeColor = '';
    export let btnHeaders = ['Lunch', 'Dinner', 'Desserts'];

    // @ Start: Local component properties
    let clickedType = 'All';
    let projects = [
        {text: 'test1', type: 'Education'},
        {text: 'test2', type: 'Personal'},
]
	let filteredProjects = projects;
    let fiterBtnStyle =
		'filter  md:w-full md:px-4 md:py-2 mb-8 font-medium text-black uppercase shadow-md dark:text-white w-[40%] h-14';
    // End: Local component properties

    // Start: Local component methods
	const filterProjects = (evt) => {
		clickedType = evt.target.textContent;
		filteredProjects = clickedType != 'All' ? projects.filter((project) => project.type == clickedType) : projects;
	};
	// End: Local component methods

    // TODO: fix better comments

</script>

<section id="projects" class="pt-20 pb-24 bg-gray-100 {darkMode ? `dark:${darkModeColor}` : ''}">
    <!-- Container -->
    <div class="relative py-8 md:py-16 xl:max-w-screen-xl xl:mx-auto {darkMode ? `dark:${darkModeColor}` : ''}">
        <!-- Heading and description -->
        <div class="relative px-2 text-center">
            <h2 class="relative text-3xl font-bold tracking-tight md:text-5xl dark:text-white">{title}</h2>

            <div class="mt-6 flex justify-center gap-3 flex-row flex-wrap md:flex-nowrap">
                {#each btnHeaders as header}
                     <button
                        class="{fiterBtnStyle}"
                        class:active="{clickedType === {header}}"
                        on:click="{filterProjects}"
                    >
                        <span class="text-lg opacity-75"> {header} </span>
                    </button>
                {/each}
                
            </div>
        </div>

        <!-- Projects -->
        <div>
            <section class="projects justify-between lg:grid lg:grid-cols-3 flex flex-col items-center">
                {#if projects.length > 0}
                    {#each filteredProjects as project}
                        <p>Test</p>
                        <!-- <HomeProjectCard
                            heading="{project.title}"
                            tools="{project.tools}"
                            text="{project.description}"
                            url="{project.url}"
                            img="{project.imageSrc}"
                            skills="{project.work}"
                            type="{project.type}"
                        /> -->
                    {/each}
                {/if}
            </section>
        </div>
    </div>
</section>