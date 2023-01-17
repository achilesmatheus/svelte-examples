<script>
  let value = 1;
  let min = 1;
  let max = 10;
</script>

<div class="wrapper">
  <h1>Selected value: {value}</h1>
  <input class="slider" type="range" bind:value {min} {max} step="1" />
  <div class="labels">
    <span>{min}</span>
    <span>{max}</span>
  </div>
</div>

<style>
  .labels {
    display: flex;
    justify-content: space-between;
  }

  .slider {
    width: 100%;
  }
</style>
