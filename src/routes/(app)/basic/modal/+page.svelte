<script>
  import Modal from "$lib/page-components/modal/preview/Modal.svelte";
  import * as CodeBlock from "$lib/page-components/modal/snippets";
  import Tabs from "$lib/components/Tabs/Tabs.svelte";
  import Tab from "$lib/components/Tabs/Tab.svelte";
  import TabContent from "$lib/components/Tabs/TabContent.svelte";
  import TabPreview from "$lib/components/Tabs/TabPreview.svelte";
</script>

<Tabs>
  <svelte:fragment slot="tab-list">
    <Tab label="App.svelte" />
    <Tab label="Modal.svelte" />
  </svelte:fragment>

  <svelte:fragment slot="tab-content">
    <TabContent>
      <CodeBlock.App />
    </TabContent>
    <TabContent>
      <CodeBlock.Modal />
    </TabContent>
    <TabPreview>
      <Modal>
        <p>A simple modal</p>
      </Modal>
    </TabPreview>
  </svelte:fragment>
</Tabs>
