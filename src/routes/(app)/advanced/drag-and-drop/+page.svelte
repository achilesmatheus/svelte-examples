<script>
  import DragElement from "$lib/page-components/drag-and-drop/preview/DragElement.svelte";
  import * as CodeBlock from "$lib/page-components/drag-and-drop/snippets";
  import Tabs from "$lib/components/Tabs/Tabs.svelte";
  import Tab from "$lib/components/Tabs/Tab.svelte";
  import TabContent from "$lib/components/Tabs/TabContent.svelte";
  import TabPreview from "$lib/components/Tabs/TabPreview.svelte";
</script>

<Tabs>
  <svelte:fragment slot="tab-list">
    <Tab label="App.svelte" />
    <Tab label="DragElement.svelte" />
  </svelte:fragment>

  <svelte:fragment slot="tab-content">
    <TabContent>
      <CodeBlock.App />
    </TabContent>
    <TabContent>
      <CodeBlock.DragElement />
    </TabContent>
    <TabPreview>
      <DragElement />
    </TabPreview>
  </svelte:fragment>
</Tabs>
