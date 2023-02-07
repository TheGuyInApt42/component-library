<script>
    import TabWrapper from "./TabWrapper.svelte";
    import TabContentItem from "./TabContentItem.svelte";
    import TabHead from "./TabHead.svelte";
    import TabHeadItem from "./TabHeadItem.svelte";
    import Menu from "../menu/Menu.svelte";
    let activeTabValue = 1;
    const handleClick = (tabValue) => () => {
        activeTabValue = tabValue;
    };

    export let menus = []

    // NOTE: https://medium.com/stackanatomy/creating-a-svelte-tabs-component-with-slot-props-37c138e0a23e


  </script>
  
  <TabWrapper>
    <TabHead>
     <TabHeadItem id={1} on:click={handleClick(1)}>Tab 1</TabHeadItem>
     <TabHeadItem id={2} on:click={handleClick(2)}>Tab 2</TabHeadItem>
     <TabHeadItem id={3} on:click={handleClick(3)}>Tab 3</TabHeadItem>
   </TabHead>
   {#each menus as item, i}
    <TabContentItem id={i+1} {activeTabValue}>
    <Menu sectionTitle={item.title} menuItems={item.content}/></TabContentItem>
    <!-- <TabContentItem id={2} {activeTabValue}>
    <Menu sectionTitle={'Dessert'} menuItems={dessert}/></TabContentItem>
    <TabContentItem id={3} {activeTabValue}>Tab 3 content</TabContentItem> -->
   {/each}
   <!-- <TabContentItem id={1} {activeTabValue}>
    <Menu sectionTitle={'Lunch'} menuItems={menu}/></TabContentItem>
   <TabContentItem id={2} {activeTabValue}>
    <Menu sectionTitle={'Dessert'} menuItems={dessert}/></TabContentItem>
   <TabContentItem id={3} {activeTabValue}>Tab 3 content</TabContentItem> -->
 </TabWrapper>