<script>
    import Tabs from "../lib/components/tabs/Tabs.svelte";
    import SimpleTabs from "../lib/components/simple-tabs/SimpleTabs.svelte";
    import ContactFooter from "../lib/components/contact-footer/ContactFooter.svelte";
    import Menu from "../lib/components/menu/Menu.svelte";
    import { onMount } from "svelte";
    let address = `<p>343 S 2nd Ave</p>
                    <p>Mount Vernon, NY 10550</p>            
                    <a href="tel:9144194033">Tel: (914)419-4033</a>`
    
    let date = new Date();
    let day = date.getDay();

    onMount(async() =>{
        let ps = document.querySelectorAll('p');
       
        for (let i = 0; i < ps.length; i++){
            if (day == ps[i].getAttribute('data-id')){
                ps[i].classList.add('current')
                console.log(ps[i]);
            }
                
        }
    })
    

    let hours = `<p data-id="1">Mon. 	11:30am – 2:45pm & 5pm – 10pm</p>
        <p data-id="2">Tue. 	11:30am – 2:45pm & 5pm – 10pm</p>
            <p data-id="3">Wed. 	11:30am – 2:45pm & 5pm – 10pm</p>
                <p data-id="4">Thu. 	11:30am – 2:45pm & 5pm – 10pm</p>
                    <p data-id="5">Fri. 	11:30am – 2:45pm & 5pm – 10pm</p>
                        <p data-id="6">Sat. 	12pm – 10pm</p>
                            <p data-id="0">Sun. 	12pm – 10pm</p>

                                <p>Holidays:   11:30am – 10pm</p>`

    
    let menu = [
        {
            name: 'Good Burger',
            price: 12,
            description: 'Delicious Burger with Cheese, Bacon, Lettuce, Tomatoes and Pickles'
        },
        {
            name: 'Good Burger',
            price: 12,
            description: 'Delicious Burger with Cheese, Bacon, Lettuce, Tomatoes and Pickles'
        },
        {
            name: 'Good Burger',
            price: 12,
            description: 'Delicious Burger with Cheese, Bacon, Lettuce, Tomatoes and Pickles'
        },
        {
            name: 'Duck Confit Tacos',
            price: 11,
            description: 'Chihuahua cheese, avocado, cilantro, pickled onions'
        },
        {
            name: 'Good Burger',
            price: 12,
            description: 'Delicious Burger with Cheese, Bacon, Lettuce, Tomatoes and Pickles'
        },
        {
            name: 'Good Burger',
            price: 12,
            description: 'Delicious Burger with Cheese, Bacon, Lettuce, Tomatoes and Pickles'
        },
        {
            name: 'Duck Confit Tacos',
            price: 11,
            description: 'Chihuahua cheese, avocado, cilantro, pickled onions'
        },
    ]

    let dessert = [
        {
            name: 'Good Burger',
            price: 12,
            description: 'Delicious Burger with Cheese, Bacon, Lettuce, Tomatoes and Pickles'
        },
        {
            name: 'Good Burger',
            price: 12,
            description: 'Delicious Burger with Cheese, Bacon, Lettuce, Tomatoes and Pickles'
        },
        {
            name: 'Good Burger',
            price: 12,
            description: 'Delicious Burger with Cheese, Bacon, Lettuce, Tomatoes and Pickles'
        },
        {
            name: 'Duck Confit Tacos',
            price: 11,
            description: 'Chihuahua cheese, avocado, cilantro, pickled onions'
        }
     
    ]
    let dinner = [
        {
            name: 'Good Burger',
            price: 12,
            description: 'Delicious Burger with Cheese, Bacon, Lettuce, Tomatoes and Pickles'
        },
        {
            name: 'Good Burger',
            price: 12,
            description: 'Delicious Burger with Cheese, Bacon, Lettuce, Tomatoes and Pickles'
        },
        {
            name: 'Good Burger',
            price: 12,
            description: 'Delicious Burger with Cheese, Bacon, Lettuce, Tomatoes and Pickles'
        },
        {
            name: 'Duck Confit Tacos',
            price: 11,
            description: 'Chihuahua cheese, avocado, cilantro, pickled onions'
        }
     
    ]
    

    let menus = [
        {
            title: 'Lunch',
            content: menu
        },
        {
            title: 'Dessert',
            content: dessert
        },
        {
            title: 'Dinner',
            content: dinner
        }
    ]

    

    
</script>

<h1 class="text-3xl">Welcome to your library project</h1>
<p>Create your package using @sveltejs/package and preview/showcase your work with SvelteKit</p>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>


<Tabs menus={menus}/>




<div class="bg-white">
    space
</div>


<ContactFooter address={address} hours={hours}/>

