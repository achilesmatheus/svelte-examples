```sv
<script>
  let leftSideList = ["Item 1", "Item 2", "Item 3"];
  let rightSideList = ["Item 4", "Item 5", "Item 6"];

  let selectedItemsAtLeft = [];
  let selectedItemsAtRight = [];

  function transferItems(to, selectedItems) {
    let result = [...to, ...selectedItems];
    return result;
  }

  function transferAll(from, to) {
    let result = [...to, ...from];
    selectedItemsAtLeft = [];
    selectedItemsAtRight = [];
    return result;
  }

  function allItemtoLeft() {
    leftSideList = transferAll(rightSideList, leftSideList);
    rightSideList = [];
  }

  function allItemtoRight() {
    rightSideList = transferAll(leftSideList, rightSideList);
    leftSideList = [];
  }

  function selectedItemsToLeft() {
    leftSideList = transferItems(leftSideList, selectedItemsAtRight);
    rightSideList = rightSideList.filter(
      (item) => !leftSideList.includes(item)
    );
    selectedItemsAtRight = [];
  }

  function selectedItemsToRight() {
    rightSideList = transferItems(rightSideList, selectedItemsAtLeft);
    leftSideList = leftSideList.filter((item) => !rightSideList.includes(item));
    selectedItemsAtLeft = [];
  }
</script>

<div class="wrapper">
  <div class="card list">
    {#each leftSideList as item (item)}
      <label for={item}>
        <input
          type="checkbox"
          name="left-list"
          bind:group={selectedItemsAtLeft}
          value={item}
          id={item}
        />
        {item}
      </label>
    {/each}
  </div>

  <!-- Controls -->
  <div class="controls">
    <button class="btn" on:click={allItemtoRight}
      ><iconify-icon icon="carbon:caret-right" /></button
    >
    <button class="btn" on:click={selectedItemsToRight}
      ><iconify-icon icon="carbon:chevron-right" /></button
    >
    <button class="btn" on:click={selectedItemsToLeft}
      ><iconify-icon icon="carbon:chevron-left" /></button
    >
    <button class="btn" on:click={allItemtoLeft}
      ><iconify-icon icon="carbon:caret-left" /></button
    >
  </div>
  <!-- end controls -->

  <div class="card list">
    {#each rightSideList as item (item)}
      <label for={item}>
        <input
          type="checkbox"
          name="right-list"
          bind:group={selectedItemsAtRight}
          value={item}
          id={item}
        />
        {item}
      </label>
    {/each}
  </div>
</div>

<style>
  .wrapper {
    display: flex;
    gap: 1rem;
    align-items: center;
  }

  .list {
    margin-top: 0;
    min-height: 240px;
    min-width: 110px;
  }

  .controls {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }

  label {
    display: flex;
    align-items: baseline;
    gap: 0.5rem;
  }

  label + label {
    margin-top: 1rem;
  }
</style>

```
