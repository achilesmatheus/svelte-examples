<script>
  import SplitPanel from "$lib/page-components/split-panel/preview/SplitPanel.svelte";
  import * as CodeBlock from "$lib/page-components/split-panel/snippets";
  import Tabs from "$lib/components/Tabs/Tabs.svelte";
  import Tab from "$lib/components/Tabs/Tab.svelte";
  import TabContent from "$lib/components/Tabs/TabContent.svelte";
  import TabPreview from "$lib/components/Tabs/TabPreview.svelte";
</script>

<Tabs>
  <svelte:fragment slot="tab-list">
    <Tab label="App.svelte" />
    <Tab label="Panel.svelte" />
  </svelte:fragment>

  <svelte:fragment slot="tab-content">
    <TabContent>
      <CodeBlock.App />
    </TabContent>
    <TabContent>
      <CodeBlock.Panel />
    </TabContent>
    <TabPreview fullWidth={true}>
      <SplitPanel>
        <h1 slot="left">Left</h1>
        <h1 slot="right">Right</h1>
      </SplitPanel>
    </TabPreview>
  </svelte:fragment>
</Tabs>
