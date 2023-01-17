<script>
  import { onMount } from "svelte";
  import Tab from "./Tab.svelte";
  import { selectedTab } from "./store";

  let tabList, tabContent;

  $: {
    if ($selectedTab === tabList?.childElementCount) {
      $selectedTab = tabList?.childElementCount - 1;
    }
  }

  function setElementsId(dataSelector) {
    const dataTab = document.querySelectorAll(dataSelector);
    dataTab.forEach((element, index) => {
      element.dataset.id = index;
    });
  }

  onMount(() => {
    setElementsId('[data-tab="tab"]');
    setElementsId('[data-tab="content"]');
  });
</script>

<div class="tabs">
  <div bind:this={tabList} class="tab-list">
    <slot name="tab-list" />
    <Tab label="Preview" />
  </div>

  <div bind:this={tabContent} class="tab-content">
    <slot name="tab-content" />
  </div>
</div>

<style>
  .tab-list {
    display: flex;
    margin: 0 auto;
    padding: 0.5rem;
    background-color: var(--white);
    box-shadow: rgba(60, 64, 67, 0.15) 0px 2px 2px 0px,
      #ffffff26 0px 1px 3px 1px;
    border-radius: 0.2rem;
  }

  .tab-content {
    margin-top: 0.5rem;
    min-height: 300px;
  }
</style>
