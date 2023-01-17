```sv
<script>
  let open = false;
</script>

{#if open}
  <div class="wrapper">
    <div class="modal">
      <div class="modal__title">
        <h1>Modal</h1>
      </div>
      <slot />
      <hr />
      <div class="modal__footer">
        <button
          class="btn"
          on:click={() => {
            alert("Confirm button pressed!");
            open = false;
          }}>Confirm</button
        >
        <button class="btn" on:click={() => (open = false)}>Cancel</button>
      </div>
    </div>
  </div>
{:else}
  <button class="btn" on:click={() => (open = true)}>Open modal</button>
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
</style>

```
