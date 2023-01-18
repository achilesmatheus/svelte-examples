<script>
  import FloatingMenu from "$lib/components/FloatingMenu/FloatingMenu.svelte";
  import Layout from "$lib/components/Layout.svelte";
  import Select from "$lib/components/Select/Select.svelte";
  import { menu } from "$lib/components/FloatingMenu/menu";

  let menuData = menu;
  let selected = "basic";
</script>

<a href="/">
  <h3>Back to home page</h3>
  ;
</a>
<Layout>
  <Select menu={menuData} bind:selected slot="select" />
  <FloatingMenu menu={menuData} bind:selected slot="floating-menu" />
  <slot slot="main-content" />
</Layout>

<style>
  a {
    text-align: center;
    color: var(--dark);
    text-decoration: none;
  }

  a:hover {
    text-decoration: underline;
  }

  h3 {
    margin-top: 1rem;
  }
</style>
