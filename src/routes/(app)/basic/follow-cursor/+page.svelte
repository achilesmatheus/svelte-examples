<script>
  import Cursor from "$lib/page-components/follow-cursor/preview/Cursor.svelte";
  import * as CodeBlock from "$lib/page-components/follow-cursor/snippets";
  import Tabs from "$lib/components/Tabs/Tabs.svelte";
  import Tab from "$lib/components/Tabs/Tab.svelte";
  import TabContent from "$lib/components/Tabs/TabContent.svelte";
  import TabPreview from "$lib/components/Tabs/TabPreview.svelte";
</script>

<Tabs>
  <svelte:fragment slot="tab-list">
    <Tab label="App.svelte" />
    <Tab label="Cursor.svelte" />
  </svelte:fragment>

  <svelte:fragment slot="tab-content">
    <TabContent>
      <CodeBlock.App />
    </TabContent>
    <TabContent>
      <CodeBlock.Cursor />
    </TabContent>
    <TabPreview>
      <Cursor />
    </TabPreview>
  </svelte:fragment>
</Tabs>
