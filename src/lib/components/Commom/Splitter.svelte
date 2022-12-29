<script>
  import { onMount } from "svelte";

  let leftContainer, splitter;

  let x, y;
  let leftWidth = 0;

  onMount(() => {
    // leftContainer.style.flex = "1";
  });

  function handleMouseUp() {
    document.removeEventListener("mousemove", handleMove);
    document.removeEventListener("mouseup", handleMouseUp);
  }

  function handleMouseDown(e) {
    // Get the current mouse position
    x = e.clientX;
    y = e.clientY;
    leftWidth = leftContainer.getBoundingClientRect().width;

    document.addEventListener("mousemove", handleMove);
    document.addEventListener("mouseup", handleMouseUp);
  }

  function handleMove(e) {
    // leftContainer.style.flex = "none";

    // How far the mouse has been moved
    const dx = e.clientX - x;
    const newLeftWidth =
      ((leftWidth + dx) * 100) /
      splitter.parentNode.getBoundingClientRect().width;
    leftContainer.style.width = `${newLeftWidth}%`;
  }
</script>

<div class="container">
  <div bind:this={leftContainer} class="container__left">
    <slot name="left" />
  </div>

  <div bind:this={splitter} on:mousedown={handleMouseDown} class="splitter" />

  <div class="container__right">
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
    width: 50%;
    display: grid;
    place-content: center;
  }

  .container__right {
    flex: 1;
  }

  .splitter {
    width: 2px;
    background-color: #cbd5e0;
    cursor: ew-resize;
    position: relative;
    transition: background-color 0.2s;
  }

  .splitter::before {
    position: absolute;
    width: 1.5rem;
    height: 1.5rem;
    display: grid;
    place-content: center;
    top: 50%;
    background-color: #cbd5e0;
    color: var(--white);
    font-weight: bold;
    border-radius: 100%;
    content: "‹›";
    transform: translate(calc(-50% + 1px), -50%);
    transition: background-color 0.2s;
  }

  .splitter:hover::before {
    background-color: var(--dark);
  }

  .splitter:hover {
    background-color: var(--dark);
  }
</style>
