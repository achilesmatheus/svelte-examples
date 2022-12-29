<script>
  import Card from "./Card.svelte";
  import FloatingMenuItem from "./FloatingMenuItem.svelte";
  import Select from "./Select.svelte";
</script>

<Select />

<div class="menu">
  <Card>
    <div class="menu__options">
      <FloatingMenuItem icon="carbon:string-text" text="Alphabet Array" />
      <FloatingMenuItem icon="carbon:string-text" text="Copy to clipboard" />
      <FloatingMenuItem icon="carbon:string-text" text="Scroll to Page Top" />
      <FloatingMenuItem icon="carbon:string-text" text="Toggle element" />
      <FloatingMenuItem icon="carbon:string-text" text="Capitalize a String" />
      <FloatingMenuItem
        icon="carbon:string-text"
        text="Remove Duplicates in an Array"
      />
      <FloatingMenuItem icon="carbon:string-text" text="Array" />
      <FloatingMenuItem icon="carbon:string-text" text="Array" />
      <FloatingMenuItem icon="carbon:string-text" text="Array" />
    </div>
  </Card>
</div>

<style>
  .menu {
    width: fit-content;
    margin: 0 auto;
  }

  .menu__options {
    display: flex;
    align-items: center;
  }
</style>
