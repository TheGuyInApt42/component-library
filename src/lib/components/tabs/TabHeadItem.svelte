<script>
    // adding active class

    export let id;
    export let activeTabValue
    export let inactiveClass = 'inline-block py-4 px-4 text-sm font-medium text-center text-gray-500 rounded-t-lg hover:text-gray-600 hover:bg-gray-50 dark:text-gray-400 dark:hover:bg-gray-800 dark:hover:text-gray-300'
    export let activeClass = 'inline-block py-4 px-4 text-sm font-medium text-center text-blue-600 bg-gray-100 rounded-t-lg active dark:bg-gray-800 dark:text-blue-500'
    const liClass = 'mr-2'
  </script>
  
  <li class={liClass} role="presentation">
    <button
      on:click
      class={activeTabValue === id ? activeClass : inactiveClass}
      id="{id}-tabhead"
      type="button"
      role="tab">
      <slot />
    </button>
  </li>