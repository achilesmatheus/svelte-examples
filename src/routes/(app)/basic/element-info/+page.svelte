<script>
  import Info from "$lib/page-components/element-info/preview/Info.svelte";
  import * as CodeBlock from "$lib/page-components/element-info/snippets";
  import Tabs from "$lib/components/Tabs/Tabs.svelte";
  import Tab from "$lib/components/Tabs/Tab.svelte";
  import TabContent from "$lib/components/Tabs/TabContent.svelte";
  import TabPreview from "$lib/components/Tabs/TabPreview.svelte";
</script>

<Tabs>
  <svelte:fragment slot="tab-list">
    <Tab label="App.svelte" />
    <Tab label="Info.svelte" />
  </svelte:fragment>

  <svelte:fragment slot="tab-content">
    <TabContent>
      <CodeBlock.App />
    </TabContent>
    <TabContent>
      <CodeBlock.Info />
    </TabContent>
    <TabPreview>
      <Info />
    </TabPreview>
  </svelte:fragment>
</Tabs>
