<script>
  export let text = "Texto de exemplo";
  export let icon = "carbon:ibm-watson-speech-to-text";
  export let href = "/";
  export let pathname = "/";
</script>

<a {href}>
  <iconify-icon
    class="menu__item"
    class:menu__item-active={href === pathname}
    data-title={text}
    {icon}
    width="20"
    height="20"
  />
</a>

<style>
  a {
    color: var(--dark);
  }
  .menu__item {
    padding: 0.5rem;
    border-radius: 0.2rem;
    cursor: pointer;
    position: relative;
  }

  .menu__item-active {
    background-color: var(--light-gray);
  }

  .menu__item:hover {
    background-color: var(--light-gray);
  }

  .menu__item:after {
    position: absolute;
    content: attr(data-title);
    display: none;
    width: max-content;
    padding: 0.5rem;
    background-color: var(--dark);
    transform: translate(-50%);
    top: -3rem;
    left: 50%;
    border-radius: 0.2rem;
    color: var(--white);
    font-size: 0.875rem;
  }

  .menu__item:before {
    content: "";
    position: absolute;
    min-width: fit-content;
    display: none;
    width: 10px;
    height: 10px;
    top: -1.35rem;
    left: 50%;
    transform: translate(-50%) rotate(45deg);
    background-color: var(--dark);
    border-radius: 0.2rem;
  }

  .menu__item:hover::after,
  *:hover::before {
    display: block;
  }
</style>
