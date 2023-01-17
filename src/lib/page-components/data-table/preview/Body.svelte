<script>
  import { dataRows } from "./data";
  import Form from "./Form.svelte";
  import Modal from "./Modal.svelte";
  import View from "./View.svelte";

  let component = null;
  let open = false;
  let selectedRow = {};

  function deleteRow(row) {
    return () => {
      $dataRows = $dataRows.filter((item) => item !== row);
    };
  }

  function editRow(row) {
    return () => {
      component = Form;
      selectedRow = row;
      open = true;
    };
  }

  function viewRow(row) {
    return () => {
      component = View;
      selectedRow = row;
      open = true;
    };
  }
</script>

<tbody>
  {#each $dataRows as row}
    <tr>
      {#each Object.values(row).slice(1) as column}
        {#if column === "controls"}
          <td>
            <iconify-icon on:click={editRow(row)} icon="carbon:edit" />
            <iconify-icon on:click={deleteRow(row)} icon="carbon:trash-can" />
            <iconify-icon on:click={viewRow(row)} icon="carbon:view" />
          </td>
        {:else}
          <td>
            {column}
          </td>
        {/if}
      {/each}
    </tr>
  {/each}
</tbody>

<Modal bind:open>
  <svelte:component this={component} {selectedRow} bind:open />
</Modal>

<style>
  tr:nth-child(even) {
    background-color: #f6f6f6;
  }

  td {
    padding: 0.5rem 0 0.5rem 1rem;
  }

  iconify-icon {
    padding: 0.2rem;
    border-radius: 0.2rem;
  }

  iconify-icon:hover {
    background-color: #f6f6f6;
    cursor: pointer;
  }
</style>
