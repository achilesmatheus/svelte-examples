<script>
  import Container from "$lib/components/Container.svelte";
  import FloatingMenu from "$lib/components/FloatingMenu/FloatingMenu.svelte";
  import Footer from "$lib/components/Footer.svelte";
  import Title from "$lib/components/Title.svelte";
</script>

<main>
  <Container>
    <Title>Svelte Toolbox</Title>
  </Container>

  <Container>
    <slot />
  </Container>
  <Footer />
</main>

<style>
  main {
    max-width: 960px;
    margin: 0 auto;
  }
</style>
