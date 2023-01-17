<script>
  import FloatingMenu from "$lib/components/FloatingMenu/FloatingMenu.svelte";
  import Layout from "$lib/components/Layout.svelte";
  import Select from "$lib/components/Select/Select.svelte";
  import { menu } from "$lib/components/FloatingMenu/menu";

  let menuData = menu;
</script>

<Layout>
  <Select menu={menuData} slot="select" />
  <FloatingMenu menu={menuData} slot="floating-menu" />
  <slot slot="main-content" />
</Layout>
