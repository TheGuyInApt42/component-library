<script lang="ts">
    import classNames from 'classnames'
    export let divClass = 'w-full'
    export let tabStyle: 'default' | 'underline' | 'filterBtn' ='default'
  </script>
  
  <div class={classNames(divClass, $$props.class)}>
    <slot {tabStyle} />
  </div>