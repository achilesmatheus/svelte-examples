```sv
<script>
  let left = 0;
  let top = 0;
  let wrapper;

  function handleMove(e) {
    left = e.pageX + "px";
    top = e.pageY + "px";
  }

  function mouseDown() {
    wrapper.style.transform = "translate(-50%, -50%) scale(1.2)";
  }

  function mouseUp() {
    wrapper.style.transform = "translate(-50%, -50%) scale(1)";
  }
</script>

<svelte:body
  on:mousemove={handleMove}
  on:mousedown={mouseDown}
  on:mouseup={mouseUp}
/>

<div bind:this={wrapper} class="wrapper" style:left style:top>
  <div class="circle" />
</div>

<style>
  .wrapper {
    width: 50px;
    height: 50px;
    border: 1px solid;
    border-radius: 50%;
    position: absolute;
    transform: translate(-50%, -50%);
    pointer-events: none;
    transition: transform 0.2s cubic-bezier(0.075, 0.82, 0.165, 1);
  }

  .circle {
    width: 25%;
    height: 25%;
    background-color: #000;
    border-radius: 50%;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    pointer-events: none;
  }
</style>

```
