<script>
  import Code from "./code.md";
  import Code2 from "./code2.md";
  import Splitter from "./Splitter.svelte";
  import Tabs from "./Tabs.svelte";
  import Title from "./Title.svelte";

  const btnText = "Copiar código";
  let btnCopy;

  let tabItems = [
    {
      title: "App",
      index: 1,
      component: Code,
    },
    {
      title: "Card",
      index: 2,
      component: Code2,
    },
    {
      title: "Tab",
      index: 3,
      component: Code2,
    },
    {
      title: "Form",
      index: 4,
      component: Code2,
    },
  ];

  tabItems = [
    ...tabItems,
    { title: "Preview", index: tabItems.length + 1, component: Title },
  ];

  const copyContent = async (element) => {
    const text = element.nextElementSibling.innerText;
    try {
      await navigator.clipboard.writeText(text);
      btnCopy.innerText = "Copiado ✓";

      setTimeout(() => (btnCopy.innerText = btnText), 1500);
    } catch (err) {
      console.error("Não foi possível copiar o conteúdo: ", err);
    }
  };
</script>

<!-- <div class="wrapper">
  <button
    bind:this={btnCopy}
    class="btn-copy"
    on:click={() => copyContent(btnCopy)}>{btnText}</button
  >
  <Code />
</div> -->

<Tabs tabs={tabItems} />

<style>
  .wrapper {
    position: relative;
  }

  .wrapper button {
    position: absolute;
    top: 5px;
    right: 5px;
    background-color: var(--white);
    border: none;
    padding: 0.5rem;
    border-radius: 0.2rem;
    cursor: pointer;
    border: 1px solid transparent;
  }

  .wrapper button:hover {
    background-color: #282c34;
    color: var(--white);
    border-color: var(--white);
  }
</style>
