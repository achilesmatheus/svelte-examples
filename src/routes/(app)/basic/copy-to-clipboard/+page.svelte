<script>
  import CopyButton from "$lib/page-components/copy-to-clipboard/preview/CopyButton.svelte";
  import * as CodeBlock from "$lib/page-components/copy-to-clipboard/snippets";
  import Tabs from "$lib/components/Tabs/Tabs.svelte";
  import Tab from "$lib/components/Tabs/Tab.svelte";
  import TabContent from "$lib/components/Tabs/TabContent.svelte";
  import TabPreview from "$lib/components/Tabs/TabPreview.svelte";
</script>

<Tabs>
  <svelte:fragment slot="tab-list">
    <Tab label="App.svelte" />
    <Tab label="CopyButton.svelte" />
  </svelte:fragment>

  <svelte:fragment slot="tab-content">
    <TabContent>
      <CodeBlock.App />
    </TabContent>
    <TabContent>
      <CodeBlock.CopyButton />
    </TabContent>
    <TabPreview>
      <CopyButton />
    </TabPreview>
  </svelte:fragment>
</Tabs>
