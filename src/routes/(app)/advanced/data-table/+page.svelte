<script>
  import DataTable from "$lib/page-components/data-table/preview/DataTable.svelte";
  import * as CodeBlock from "$lib/page-components/data-table/snippets";
  import Tabs from "$lib/components/Tabs/Tabs.svelte";
  import Tab from "$lib/components/Tabs/Tab.svelte";
  import TabContent from "$lib/components/Tabs/TabContent.svelte";
  import TabPreview from "$lib/components/Tabs/TabPreview.svelte";
</script>

<Tabs>
  <svelte:fragment slot="tab-list">
    <Tab label="App.svelte" />
    <Tab label="Table.svelte" />
    <Tab label="Header.svelte" />
    <Tab label="Body.svelte" />
    <Tab label="Modal.svelte" />
    <Tab label="Form.svelte" />
    <Tab label="View.svelte" />
    <Tab label="data.js" />
  </svelte:fragment>

  <svelte:fragment slot="tab-content">
    <TabContent>
      <CodeBlock.App />
    </TabContent>
    <TabContent>
      <CodeBlock.Table />
    </TabContent>
    <TabContent>
      <CodeBlock.Header />
    </TabContent>
    <TabContent>
      <CodeBlock.Body />
    </TabContent>
    <TabContent>
      <CodeBlock.Modal />
    </TabContent>
    <TabContent>
      <CodeBlock.Form />
    </TabContent>
    <TabContent>
      <CodeBlock.View />
    </TabContent>
    <TabContent>
      <CodeBlock.data />
    </TabContent>
    <TabPreview>
      <DataTable />
    </TabPreview>
  </svelte:fragment>
</Tabs>
