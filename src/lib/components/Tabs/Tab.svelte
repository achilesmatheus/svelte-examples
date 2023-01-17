<!-- svelte-ignore a11y-click-events-have-key-events -->
<script>
  import { selectedTab } from "./store";
  export let label = "";
  let tab;

  function selectTab() {
    $selectedTab = +tab.dataset.id;
  }
</script>

<div
  bind:this={tab}
  on:click={selectTab}
  data-tab="tab"
  class="tab-list__item"
  class:tab-list__item-active={$selectedTab === +tab?.dataset.id}
>
  {label}
</div>

<style>
  .tab-list__item {
    display: block;
    padding: 0.5rem;
    border-bottom: 2px solid #f6f6f6;
  }

  .tab-list__item-active {
    border-bottom: 2px solid var(--dark);
  }

  .tab-list__item:hover {
    cursor: pointer;
  }

  .tab-list__item:last-child {
    border: 1px solid #ff3e00;
    color: var(--dark);
    margin-left: auto;
    border-radius: 0.2rem;
  }

  .tab-list__item-active:last-child {
    background-color: #ff3e00;
    color: var(--white);
  }
</style>
