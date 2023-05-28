<script>
  import '../app.css';
  import Header from '../components/header.svelte';
  import MainNavigation from '../components/mainNavigation.svelte';

  let showMenu = false;
  const toggleMenu = () => (showMenu = !showMenu);
</script>

<div class="relative h-full flex flex-col bg-brand-beige font-light font-serif">
  <Header {toggleMenu} />
  {#if showMenu}
    <div
      on:mousedown={() => (showMenu = false)}
      class="absolute top-0 left-0 h-full w-full bg-black opacity-60 cursor-pointer"
    />
    <MainNavigation {toggleMenu} />
  {/if}
  <main class="grow-1 h-full">
    <slot />
  </main>
</div>
