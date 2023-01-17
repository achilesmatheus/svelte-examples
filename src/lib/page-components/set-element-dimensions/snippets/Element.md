```sv
<script>
  let heightValue = 50;
  let widthValue = 50;

  $: width = `${widthValue}px`;
  $: height = `${heightValue}px`;
</script>

<label for="">Height:
  <input type="range" min="20" max="150" bind:value={heightValue}>
</label>
<label for="">Width:
  <input type="range" min="20" max="150" bind:value={widthValue}>
</label>

<div class="card" style:--width={width} style:--height={height}>Div</div>

<style>
  .card {
    width: var(--width);
    height: var(--height);
  }

  label {
    display: flex;
  }
</style>
```
