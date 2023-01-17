<script>
  let editing = false;
  let content;

  function handleChange() {
    if (content.textContent.length === 0) {
      content.focus();
      return;
    }
    const range = document.createRange();
    const sel = window.getSelection();

    range.setStart(content, 1);
    range.collapse(true);
    sel.removeAllRanges();
    sel.addRange(range);
  }
</script>

<label for="edit">Enable editing:</label>
<input
  type="checkbox"
  id="edit"
  bind:checked={editing}
  on:change={handleChange}
/>
<div class="card" bind:this={content} contenteditable={editing}>Content</div>
