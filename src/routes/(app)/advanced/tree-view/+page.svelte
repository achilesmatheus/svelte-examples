<script>
  import TreeView from "$lib/page-components/tree-view/preview/TreeView.svelte";
  import * as CodeBlock from "$lib/page-components/tree-view/snippets";
  import Tabs from "$lib/components/Tabs/Tabs.svelte";
  import Tab from "$lib/components/Tabs/Tab.svelte";
  import TabContent from "$lib/components/Tabs/TabContent.svelte";
  import TabPreview from "$lib/components/Tabs/TabPreview.svelte";
</script>

<Tabs>
  <svelte:fragment slot="tab-list">
    <Tab label="App.svelte" />
    <Tab label="File.svelte" />
    <Tab label="Folder.svelte" />
  </svelte:fragment>

  <svelte:fragment slot="tab-content">
    <TabContent>
      <CodeBlock.App />
    </TabContent>
    <TabContent>
      <CodeBlock.File />
    </TabContent>
    <TabContent>
      <CodeBlock.Folder />
    </TabContent>
    <TabPreview>
      <TreeView />
    </TabPreview>
  </svelte:fragment>
</Tabs>
