```sv
<script>
  import File from "./File.svelte";
  import Folder from "./Folder.svelte";

  let filesAndFolders = [
    {
      type: "folder",
      name: "Important work stuff",
      files: [{ type: "file", name: "quarterly-results.xlsx" }],
    },
    {
      type: "folder",
      name: "Animal GIFs",
      files: [
        {
          type: "folder",
          name: "Dogs",
          files: [
            { type: "file", name: "treadmill.gif" },
            { type: "file", name: "rope-jumping.gif" },
          ],
        },
        {
          type: "folder",
          name: "Goats",
          files: [
            { type: "file", name: "parkour.gif" },
            { type: "file", name: "rampage.gif" },
          ],
        },
        { type: "file", name: "cat-roomba.gif" },
        { type: "file", name: "duck-shuffle.gif" },
        { type: "file", name: "monkey-on-a-pig.gif" },
      ],
    },
    { type: "file", name: "TODO.md" },
  ];
</script>

<h4>
  Tree view - <a href="https://svelte.dev/examples/svelte-self"
    >Svelte examples clone</a
  >
</h4>

<div class="wrapper">
  {#each filesAndFolders as item}
    {#if item.type === "folder"}
      <Folder name={item.name} files={item.files} />
    {:else}
      <File name={item.name} />
    {/if}
  {/each}
</div>

<style>
  .wrapper {
    margin: 0 auto;
    width: 300px;
  }
</style>

```
