<script>
  import FloatingMenu from "$lib/components/FloatingMenu/FloatingMenu.svelte";
  import Select from "$lib/components/Select/Select.svelte";
  import Tabs from "$lib/components/Tabs.svelte";
  import { tabItems } from "$lib/page-components/counter/tab-items";
  import Counter from "$lib/page-components/counter/preview/Counter.svelte";
  import Container from "$lib/components/Container.svelte";

  let selected;
  let preview = Counter;
</script>

<Select on:change={(e) => (selected = e.target.value)} />
<FloatingMenu {selected} />

<Container>
  <Tabs tabs={tabItems} Preview={preview} />
</Container>
