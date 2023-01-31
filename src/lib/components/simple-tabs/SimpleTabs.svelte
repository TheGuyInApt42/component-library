<script>
    // Exports
    export let title = "Menu";
    export let darkMode = false;
    export let darkModeColor = '';
    export let darkModeTextColor = ''
    export let btnHeaders = ['Lunch', 'Dinner', 'Desserts'];
    let clickedType = 'All';
    export let tabContent = [
        /* {text: 'test1', type: 'Lunch'},
        {text: 'test2', type: 'Dinner'}, */
    ]

    // * Start: Local component properties
    
	let filteredContent = tabContent;
    let fiterBtnStyle =
		`filter  md:w-full md:px-4 md:py-2 mb-8 font-medium text-black uppercase shadow-md w-[40%] h-14`;
    // End: Local component properties

    // Start: Local component methods
	const filterContent = (evt) => {
		clickedType = evt.target.textContent;
		filteredContent = clickedType != 'All' ? tabContent.filter((content) => content.type == clickedType) : tabContent;
	};
	// End: Local component methods

    // TODO: fix better comments

</script>

<section id="tabs" class="pt-20 pb-24 bg-gray-100 {darkMode ? `dark:${darkModeColor}` : ''}">
    <!-- Container -->
    <div class="relative py-8 md:py-16 xl:max-w-screen-xl xl:mx-auto {darkMode ? `dark:${darkModeColor}` : ''}">
        <!-- Heading and description -->
        <div class="relative px-2 text-center">
            <h2 class="relative text-3xl font-bold tracking-tight md:text-5xl {darkMode ? `dark:${darkModeTextColor}` : ''}">{title}</h2>

            <div class="mt-6 flex justify-center gap-3 flex-row flex-wrap md:flex-nowrap">
                {#each btnHeaders as header}
                     <button
                        class="{fiterBtnStyle}"
                        class:active="{clickedType === {header}}"
                        on:click="{filterContent}"
                    >
                        <span class="text-lg opacity-75"> {header} </span>
                    </button>
                {/each}
                
            </div>
        </div>

        <!-- Projects -->
        <div>
            <section class="tabbed-content justify-between lg:grid lg:grid-cols-3 flex flex-col items-center">
                {#if tabContent.length > 0}
                    {#each filteredContent as content}
                        <slot>{content}</slot>
                    {/each}
                {/if}
            </section>
        </div>
    </div>
</section>