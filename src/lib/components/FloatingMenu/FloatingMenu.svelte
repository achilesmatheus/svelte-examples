<script>
  import Card from "../Card.svelte";
  import FloatingMenuItem from "./FloatingMenuItem.svelte";
  import { page } from "$app/stores";

  $: pathname = $page.url.pathname;

  export let menu;
  export let selected = $page.url.pathname.split("/")[1];
</script>

{#if selected}
  <div class="menu">
    <Card>
      <div class="menu__options">
        {#each menu[selected] as { text, icon, href }}
          <FloatingMenuItem {icon} {text} {href} {pathname} />
        {/each}
      </div>
    </Card>
  </div>
{/if}

<style>
  .menu {
    width: fit-content;
    margin: 0 auto;
  }

  .menu__options {
    display: flex;
    align-items: center;
  }
</style>
