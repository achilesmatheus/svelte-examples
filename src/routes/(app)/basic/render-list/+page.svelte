<script>
  import Snippet from "$lib/page-components/render-list/preview/PreviewComponent.svelte";
  import * as CodeBlock from "$lib/page-components/render-list/snippets";
  import Tabs from "$lib/components/Tabs/Tabs.svelte";
  import Tab from "$lib/components/Tabs/Tab.svelte";
  import TabContent from "$lib/components/Tabs/TabContent.svelte";
  import TabPreview from "$lib/components/Tabs/TabPreview.svelte";
</script>

<Tabs>
  <svelte:fragment slot="tab-list">
    <Tab label="App.svelte" />
    <Tab label="List.svelte" />
  </svelte:fragment>

  <svelte:fragment slot="tab-content">
    <TabContent>
      <CodeBlock.App />
    </TabContent>
    <TabContent>
      <CodeBlock.List />
    </TabContent>
    <TabPreview>
      <Snippet />
    </TabPreview>
  </svelte:fragment>
</Tabs>
