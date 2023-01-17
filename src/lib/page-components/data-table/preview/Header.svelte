<script>
  import { dataRows } from "./data";
  export let dataHeaders = [];

  let initialData = $dataRows.find((item) => item.id === 1);

  $dataRows = $dataRows.sort((a, b) => a.age - b.age);

  const sortTypes = {
    number: {
      asc: (a, b) => a - b,
      desc: (a, b) => b - a,
    },
    string: {
      asc: (a, b) => {
        if (a > b) return 1;
        else if (a < b) return -1;
        return 0;
      },
      desc: (a, b) => {
        if (a < b) return 1;
        else if (a > b) return -1;
        return 0;
      },
    },
  };

  function sortElements(e, key) {
    const keyType = typeof $dataRows[0][key];
    let sortFunction = sortTypes[keyType]["asc"];
    if (initialData === $dataRows[0]) {
      $dataRows = $dataRows.sort((a, b) => sortFunction(a[key], b[key]));
    } else {
      sortFunction = sortTypes[keyType]["desc"];
      $dataRows = $dataRows.sort((a, b) => sortFunction(a[key], b[key]));
      initialData = $dataRows[0];
    }
  }
</script>

<thead>
  <tr>
    {#each dataHeaders as { key, value }, i}
      <th
        data-id={key}
        on:click={(e) => sortElements(e, key)}
        colspan={dataHeaders.length - 1 === i ? dataHeaders.length : ""}
      >
        {value}
      </th>
    {/each}
  </tr>
</thead>

<style>
  th {
    background-color: var(--dark);
    color: #fff;
    text-align: left;
    padding: 0.5rem 1rem;
    cursor: pointer;
  }

  th:hover {
    background-color: #ff3e00;
  }

  th:first-child {
    border-top-left-radius: 0.2rem;
  }

  th:last-child {
    border-top-right-radius: 0.2rem;
  }
</style>
