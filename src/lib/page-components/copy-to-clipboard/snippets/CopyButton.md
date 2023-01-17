```sv
<script>
  let card = null;
  const buttonText = "Copy";

  async function copyContent(e, element) {
    const text = element.innerText;
    const button = e.currentTarget;
    try {
      await navigator.clipboard.writeText(text);
      button.innerText = "Done ✓";

      setTimeout(() => (button.innerText = buttonText), 1500);
    } catch (err) {
      console.error("Error while coping code: ", err);
    }
  }
</script>

<button class="btn" on:click={(e) => copyContent(e, card)}>{buttonText}</button>
<div class="card" bind:this={card}>This text will be copied</div>

<label for="paste">Paste here</label>
<input type="text" id="paste" />

```
