<script>
  import CodeBlock from "../lib/components/Commom/CodeBlock.svelte";
  import Container from "../lib/components/Commom/Container.svelte";
  import FloatingMenu from "../lib/components/Commom/FloatingMenu.svelte";
  import Footer from "../lib/components/Commom/Footer.svelte";
  import Layout from "../lib/components/Commom/Layout.svelte";
  import Title from "../lib/components/Commom/Title.svelte";
</script>

<Layout>
  <Container>
    <Title>Svelte Toolbox</Title>
  </Container>
  <Container>
    <FloatingMenu />
  </Container>
  <Container>
    <CodeBlock />
  </Container>
  <Footer />
</Layout>

<style>
  @import "../styles/reset.css";
  @import "../styles/global.css";
  @import "../styles/highlight.css";
</style>
