<script>
  import { selectedTab } from "./store";

  let preview;
  export let fullWidth = false;
</script>

<div
  bind:this={preview}
  class="tab-content__item"
  data-tab="content"
  class:tab-content__item-active={$selectedTab === +preview?.dataset.id}
>
  <span>Preview components has default styles</span>
  <div class="preview-block" class:fullWidth>
    <slot />
  </div>
</div>

<style>
  .tab-content__item {
    display: none;
  }

  .tab-content__item-active {
    display: block;
  }

  .tab-content__item span {
    display: inline-block;
    width: 100%;
    text-align: center;
    color: var(--dark);
  }

  .preview-block {
    padding: 0.5rem;
    display: grid;
    place-content: center;
    border: 4px dashed #d6d6d6;
  }

  .fullWidth {
    place-content: unset;
  }
</style>
