```sv
<script>
  let text = "Div text";
  let editing = false;

  function handleDblClick() {
    editing = !editing;
  }

  function handleFocusOut() {
    editing = false;
  }
</script>

<p>Double click on button to edit text. Click outside to end.</p>

<button class="btn" on:dblclick={handleDblClick} on:focusout={handleFocusOut} contenteditable={editing}>Button</button>
```
