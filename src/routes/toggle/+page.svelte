<script>
  import { tabItems } from "$lib/page-components/toggle/tab-items";
  import Toggle from "$lib/page-components/toggle/preview/Toggle.svelte";
  import Tabs from "$lib/components/Tabs.svelte";

  let preview = Toggle;
</script>

<Tabs tabs={tabItems} Preview={preview} />
