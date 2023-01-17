<script>
  import Element from "$lib/page-components/set-element-dimensions/preview/Element.svelte";
  import * as CodeBlock from "$lib/page-components/set-element-dimensions/snippets";
  import Tabs from "$lib/components/Tabs/Tabs.svelte";
  import Tab from "$lib/components/Tabs/Tab.svelte";
  import TabContent from "$lib/components/Tabs/TabContent.svelte";
  import TabPreview from "$lib/components/Tabs/TabPreview.svelte";
</script>

<Tabs>
  <svelte:fragment slot="tab-list">
    <Tab label="App.svelte" />
    <Tab label="Element.svelte" />
  </svelte:fragment>

  <svelte:fragment slot="tab-content">
    <TabContent>
      <CodeBlock.App />
    </TabContent>
    <TabContent>
      <CodeBlock.Element />
    </TabContent>
    <TabPreview>
      <Element />
    </TabPreview>
  </svelte:fragment>
</Tabs>
