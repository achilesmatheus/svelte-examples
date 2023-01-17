<script>
  import CopyButton from "../CopyButton.svelte";
  import { selectedTab } from "./store";

  let content;
</script>

<div
  bind:this={content}
  class="tab-content__item"
  data-tab="content"
  class:tab-content__item-active={$selectedTab === +content?.dataset.id}
>
  <CopyButton />
  <slot />
</div>

<style>
  .tab-content__item {
    display: none;
    position: relative;
  }

  .tab-content__item-active {
    display: block;
  }
</style>
