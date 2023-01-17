<script>
  import Tasks from "$lib/page-components/update-array/preview/Tasks.svelte";
  import * as CodeBlock from "$lib/page-components/update-array/snippets";
  import Tabs from "$lib/components/Tabs/Tabs.svelte";
  import Tab from "$lib/components/Tabs/Tab.svelte";
  import TabContent from "$lib/components/Tabs/TabContent.svelte";
  import TabPreview from "$lib/components/Tabs/TabPreview.svelte";
</script>

<Tabs>
  <svelte:fragment slot="tab-list">
    <Tab label="App.svelte" />
    <Tab label="Tasks.svelte" />
  </svelte:fragment>

  <svelte:fragment slot="tab-content">
    <TabContent>
      <CodeBlock.App />
    </TabContent>
    <TabContent>
      <CodeBlock.Tasks />
    </TabContent>
    <TabPreview>
      <Tasks />
    </TabPreview>
  </svelte:fragment>
</Tabs>
