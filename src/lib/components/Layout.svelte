<script>
  import Container from "$lib/components/Container.svelte";
  import Footer from "$lib/components/Footer.svelte";
  import Title from "$lib/components/Title.svelte";
</script>

<main>
  <Container>
    <Title>Snippets</Title>
  </Container>

  <Container>
    <slot name="select" />
  </Container>

  <Container>
    <slot name="floating-menu" />
  </Container>

  <Container>
    <slot name="main-content" />
  </Container>

  <Footer />
</main>

<style>
  main {
    max-width: 960px;
    margin: 0 auto;
    display: grid;
    height: 100vh;
    grid-template-rows: auto auto auto 1fr auto;
  }
</style>
