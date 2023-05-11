<script lang="ts">
  import { drawerStore } from '@skeletonlabs/skeleton'

  const menuItems = [
    {
      label: 'menu item one',
      url: '/1',
    },
    {
      label: 'menu item two',
      url: '/2',
    },
    {
      label: 'menu item three',
      url: '/3',
    },
    {
      label: 'menu item four',
      url: '/4',
    },
  ]

  const closeDrawer = drawerStore.close
</script>

<nav class="list-nav p-4">
  <ul>
    {#each menuItems as item}
      <li><a href={item.url} on:click={closeDrawer}>{item.label}</a></li>
    {/each}
  </ul>
</nav>
