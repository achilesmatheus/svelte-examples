<script>
  import TransferList from "$lib/page-components/transfer-list/preview/TransferList.svelte";
  import * as CodeBlock from "$lib/page-components/transfer-list/snippets";
  import Tabs from "$lib/components/Tabs/Tabs.svelte";
  import Tab from "$lib/components/Tabs/Tab.svelte";
  import TabContent from "$lib/components/Tabs/TabContent.svelte";
  import TabPreview from "$lib/components/Tabs/TabPreview.svelte";
</script>

<Tabs>
  <svelte:fragment slot="tab-list">
    <Tab label="App.svelte" />
    <Tab label="Transfer List.svelte" />
  </svelte:fragment>

  <svelte:fragment slot="tab-content">
    <TabContent>
      <CodeBlock.App />
    </TabContent>
    <TabContent>
      <CodeBlock.TransferList />
    </TabContent>
    <TabPreview>
      <TransferList />
    </TabPreview>
  </svelte:fragment>
</Tabs>
