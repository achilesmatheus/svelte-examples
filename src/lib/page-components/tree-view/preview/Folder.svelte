<script>
  import { slide } from "svelte/transition";

  import File from "./File.svelte";

  export let name = "";
  export let files = [];

  let open = false;
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<div class="folder" on:click={() => (open = !open)}>
  <iconify-icon icon="carbon:folder" />
  {name}
</div>

<!-- svelte-ignore a11y-click-events-have-key-events -->
{#if open}
  <ul transition:slide={{ duration: 300 }}>
    {#each files as item}
      <li>
        {#if item.type === "folder"}
          <svelte:self name={item.name} files={item.files} />
        {:else}
          <File name={item.name} />
        {/if}
      </li>
    {/each}
  </ul>
{/if}

<style>
  .folder {
    cursor: pointer;
    display: flex;
    align-items: stretch;
    gap: 0.5rem;
  }

  ul {
    padding: 0;
    margin: 0 0.5em;
    list-style: none;
    border-left: 1px solid #eee;
  }
</style>
