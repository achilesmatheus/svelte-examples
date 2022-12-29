<footer>
  <a href="https://kit.svelte.dev/">
    Made with
    <iconify-icon
      icon="carbon:logo-svelte"
      style="color: #ff3e00;"
      width="20"
      height="20"
    />
  </a>
</footer>

<style>
  footer {
    display: flex;
    justify-content: center;
    padding: 1rem 0;
  }

  footer a {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    width: fit-content;
    text-decoration: none;
    color: var(--dark);
  }

  footer a:hover {
    text-decoration: underline;
  }
</style>
