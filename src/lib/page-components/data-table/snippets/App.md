```sv
<script>
  import { dataRows, originalData } from "./data";
  import Body from "./Body.svelte";
  import Header from "./Header.svelte";
  import Table from "./Table.svelte";

  const dataHeaders = [
    { key: "name", value: "Name" },
    { key: "age", value: "Age" },
    { key: "country", value: "Country" },
  ];

  function resetDataTable() {
    $dataRows = [...originalData];
  }
</script>

<button class="btn" on:click={resetDataTable}>Reset data</button>

<Table>
  <Header slot="table-header" {dataHeaders} />
  <Body slot="table-body" />
</Table>

<style>
  .btn {
    margin-bottom: 1rem;
  }
</style>

```
