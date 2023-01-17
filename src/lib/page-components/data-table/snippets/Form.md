```sv
<script>
  import { dataRows } from "./data";
  export let selectedRow = {};
  export let open;

  function closeModal() {
    open = false;
  }

  function handleSubmit(e) {
    e.preventDefault();
    const form = e.currentTarget;
    const formData = new FormData(form);
    const result = {};

    for (let [key, value] of formData.entries()) {
      if (key === "age") value = +value;
      result[key] = value;
    }

    const rowIndex = $dataRows.findIndex((item) => item === selectedRow);
    $dataRows[rowIndex] = { ...selectedRow, ...result };

    closeModal();
  }
</script>

<form on:submit={handleSubmit}>
  <label for="name">
    Name:
    <input type="text" name="name" id="name" value={selectedRow.name ?? ""} />
  </label>
  <label for="age">
    Age:
    <input type="text" name="age" id="age" value={selectedRow.age ?? ""} />
  </label>
  <label for="country">
    Country:
    <input
      type="text"
      name="country"
      id="country"
      value={selectedRow.country ?? ""}
    />
  </label>
  <div class="controls">
    <button class="btn" type="submit">Save</button>
    <button class="btn" type="button" on:click={closeModal}>Cancel</button>
  </div>
</form>

<style>
  form {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
  }

  .controls {
    display: flex;
    gap: 0.5rem;
  }
</style>

```
