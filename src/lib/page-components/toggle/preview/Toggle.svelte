<script>
  let contentShowed = false;
  function toggleContent() {
    contentShowed = !contentShowed;
  }
</script>

<button class="btn" on:click={toggleContent}> Toggle content</button>

{#if contentShowed}
  <div class="card">Content</div>
{/if}
