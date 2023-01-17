```sv
<script>
  export let open = false;

  function closeModal() {
    open = false;
  }
</script>

{#if open}
  <div class="wrapper">
    <div class="modal">
      <div class="modal__title">
        <h1>Modal</h1>
        <span on:click={closeModal}>x</span>
      </div>
      <slot />
    </div>
  </div>
{:else}
  <slot name="handler" {open} />
{/if}

<style>
  .wrapper {
    width: 100vw;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.5);
    position: fixed;
    left: 0;
    top: 0;
    display: grid;
    place-content: center;
  }

  .modal {
    border: 1px solid;
    padding: 1rem;
    background-color: #fff;
    min-width: 200px;
  }

  .modal__title {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .modal__title span {
    display: block;
    padding: 0.2rem 0.5rem;
  }

  .modal__title span:hover {
    background-color: #f6f6f6;
    cursor: pointer;
  }
</style>

```
