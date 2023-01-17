```sv
<script>
  let leftContainer, rightContainer, container, splitter;
  let x, y;
  let leftWidth = 0;
  let dragging = false;

  let minWidth = false;

  function handleMouseDown(e) {
    dragging = true;
    x = e.clientX;
    y = e.clientY;
    leftWidth = leftContainer.getBoundingClientRect().width;
  }

  function handleMove(e) {
    if (dragging) {
      const dx = e.clientX - x;
      const newLeftWidth =
        ((leftWidth + dx) * 100) / container.getBoundingClientRect().width;

      leftContainer.style.width = `${newLeftWidth}%`;
    }
  }

  function handleMouseUp(e) {
    dragging = false;
  }

  function setMinWidth(e) {
    minWidth = !minWidth;

    e.currentTarget.innerText = minWidth ? "Min width fixed" : "Set min width";
  }
</script>

<svelte:body on:mousemove={handleMove} on:mouseup={handleMouseUp} />

<div class="btn_group">
  <button class="btn" on:click={setMinWidth}>Set min width</button>
</div>

<div bind:this={container} class="container">
  <div bind:this={leftContainer} class="container__left" class:minWidth>
    <slot name="left" />
  </div>

  <div bind:this={splitter} on:mousedown={handleMouseDown} class="splitter" />

  <div bind:this={rightContainer} class="container__right" class:minWidth>
    <slot name="right" />
  </div>
</div>

<style>
  .container {
    display: flex;
    border: 1px solid #cbd5e0;
    border-radius: 0.2rem;
    height: 20rem;
  }

  .container__left,
  .container__right {
    min-width: 0;
    overflow: hidden;
    min-height: 5rem;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 50%;
  }

  .minWidth {
    min-width: fit-content;
  }

  .container__right {
    flex: 1;
  }

  .splitter {
    width: 8px;
    background-color: #cbd5e0;
    cursor: ew-resize;
    position: relative;
  }

  .splitter:hover {
    background-color: var(--dark);
  }

  .btn_group {
    width: fit-content;
    margin: 0.5rem auto;
  }
</style>

```
