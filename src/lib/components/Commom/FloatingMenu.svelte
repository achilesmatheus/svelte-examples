<script>
  import Card from "./Card.svelte";
  import FloatingMenuItem from "./FloatingMenuItem.svelte";
</script>

<div class="menu">
  <Card>
    <div class="menu__options">
      <FloatingMenuItem />
      <FloatingMenuItem />
      <FloatingMenuItem />
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
