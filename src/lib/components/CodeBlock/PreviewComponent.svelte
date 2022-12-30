<script>
  import Card from "../Card.svelte";

  export let Preview;
</script>

<Card>
  <h2>Result</h2>
  <div class="container-bordered">
    <svelte:component this={Preview} />
  </div>
</Card>

<style>
  .container-bordered {
    border: 4px dashed #ddd;
    padding: 1rem;
  }
  h2 {
    text-align: center;
  }
</style>
