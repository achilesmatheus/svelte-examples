<script>
  import Container from "../lib/components/Commom/Container.svelte";
  import FloatingMenu from "../lib/components/Commom/FloatingMenu.svelte";
  import Title from "../lib/components/Commom/Title.svelte";
</script>

<Container>
  <Title>Svelte toolbox</Title>
</Container>
<Container>
  <FloatingMenu />
</Container>

<style>
  @import "../styles/reset.css";
  @import "../styles/global.css";
</style>
