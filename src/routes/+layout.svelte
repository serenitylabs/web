<script lang="ts">
  // The ordering of these imports is critical to your app working properly
  import '@skeletonlabs/skeleton/themes/theme-skeleton.css'
  // If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
  import '@skeletonlabs/skeleton/styles/skeleton.css'
  // Most of your app wide CSS should be put in this file
  import '../app.postcss'

  import { AppBar, AppShell, Drawer, LightSwitch } from '@skeletonlabs/skeleton'
  import BurgerMenu from '$lib/components/BurgerMenu.svelte'
  import Navigation from '$lib/components/Navigation.svelte'
  import Logo from '$lib/components/Logo.svelte'
  import IconSkull from '~icons/mdi/skull-scan'
</script>

<Drawer><Navigation /></Drawer>

<AppShell slotSidebarLeft="bg-surface-500/5 w-0 lg:w-56">
  <svelte:fragment slot="header"
    ><AppBar>
      <svelte:fragment slot="lead">
        <div class="flex items-center space-x-4">
          <BurgerMenu />
          <Logo />
        </div>
      </svelte:fragment>
      <svelte:fragment slot="trail">
        <LightSwitch />
        <button type="button" class="btn-icon variant-filled"
          ><IconSkull /></button
        >
      </svelte:fragment>
    </AppBar></svelte:fragment
  >
  <svelte:fragment slot="sidebarLeft"><Navigation /></svelte:fragment>
  <slot />
</AppShell>
