<script>
  export let component;

  const btnText = "Copiar código";

  const copyContent = async (element) => {
    const text = element.nextElementSibling.innerText;
    try {
      await navigator.clipboard.writeText(text);
      element.innerText = "Copiado ✓";

      setTimeout(() => (element.innerText = btnText), 1500);
    } catch (err) {
      console.error("Não foi possível copiar o conteúdo: ", err);
    }
  };
</script>

<div class="wrapper">
  <button class="copy" on:click={(e) => copyContent(e.target)}>{btnText}</button
  >
  <svelte:component this={component} />
</div>

<style>
  .wrapper {
    position: relative;
  }

  .wrapper button.copy {
    position: absolute;
    top: 5px;
    right: 5px;
    background-color: var(--white);
    color: var(--dark);
    border: none;
    padding: 0.5rem;
    border-radius: 0.2rem;
    cursor: pointer;
    border: 1px solid transparent;
  }

  .wrapper button.copy:hover {
    background-color: #282c34;
    color: var(--white);
    border-color: var(--white);
  }
</style>
