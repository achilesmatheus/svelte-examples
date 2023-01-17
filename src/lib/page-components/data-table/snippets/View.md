```sv
<script>
  // Function to convert first letter to uppercase
  import captalize from "$lib/helpers/captalize";
  export let open;
  export let selectedRow;

  function closeModal() {
    open = false;
  }
</script>

<div class="wrapper">
  {#each Object.entries(selectedRow).slice(0, -1) as [key, value]}
    <p><strong>{captalize(key)}: </strong>{value}</p>
  {/each}
</div>

<button class="btn" on:click={closeModal}>Close</button>

```
