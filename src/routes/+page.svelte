<script>
  import Card from "../lib/components/Card.svelte";
  import Container from "../lib/components/Container.svelte";
  import Footer from "../lib/components/Footer.svelte";
  import Title from "../lib/components/Title.svelte";
</script>

<div class="wrapper">
  <Container>
    <Title>Svelte snippets</Title>
    <p>Snippets to help you with upcoming projects. Choose one below</p>
    <a
      href="https://github.com/achilesmatheus"
      target="_blank"
      rel="noreferrer"
    >
      <iconify-icon width="32" icon="carbon:logo-github" />
    </a>
  </Container>

  <Container>
    <div class="cards">
      <a class="cards__link" href="/basic"> Basic </a>
      <a class="cards__link" href="/advanced"> Advanced </a>
      <a class="cards__link cards__link-inactive" href="/">
        Animations.
        <i>Coming soon...</i>
      </a>
      <a class="cards__link cards__link-inactive" href="/">
        With libraries.
        <i>Coming soon...</i>
      </a>
    </div>
  </Container>
  <Footer />
</div>

<style>
  div.wrapper {
    max-width: 960px;
    margin: 0 auto;
    text-align: center;
    height: 100vh;
    display: grid;
    grid-template-rows: auto 1fr auto;
  }

  .cards {
    display: grid;
    grid-template-columns: repeat(2, minmax(min-content, 250px));
    gap: 1rem;
    justify-content: center;
  }

  a {
    text-decoration: none;
    color: var(--dark);
  }

  .cards__link {
    background-color: #fff;
    padding: 2rem 4rem;
    transition: 0.15s ease;
    box-shadow: rgba(60, 64, 67, 0.15) 0px 2px 2px 0px,
      #ffffff26 0px 1px 3px 1px;
  }

  .cards__link:hover {
    transform: translateY(-5px);
    box-shadow: rgba(0, 0, 0, 0.1) 0px 10px 15px -3px,
      rgba(0, 0, 0, 0.05) 0px 4px 6px -2px;
  }

  .cards__link-inactive {
    box-shadow: none;
    border: 1px solid #d6d6d6;
    background-color: transparent;
    cursor: default;
  }

  .cards__link-inactive:hover {
    transform: none;
    box-shadow: none;
  }
</style>
