<!-- svelte-ignore a11y-click-events-have-key-events -->
<script>
  let activeTab = 1;
  export let tabs = [{}];

  function handleClick(tab) {
    return () => {
      activeTab = tab;
    };
  }
</script>

<div class="tabs">
  <div class="tab">
    {#each tabs as { title, index }}
      <span
        on:click={handleClick(index)}
        class="tab__item"
        class:tab__item-checked={activeTab === index}>{title}</span
      >
    {/each}
  </div>

  <div class="content">
    {#each tabs as { index, component }}
      <div
        class="content__item"
        class:content__item-active={activeTab === index}
      >
        <svelte:component this={component} />
      </div>
    {/each}
  </div>
</div>

<style>
  .tab {
    display: flex;
    margin: 0 auto;
    padding: 0.5rem;
    background-color: var(--white);
    /* width: fit-content; */
    box-shadow: rgba(60, 64, 67, 0.15) 0px 2px 2px 0px,
      #ffffff26 0px 1px 3px 1px;
    border-radius: 0.2rem;
  }

  .tab__item {
    display: block;
    padding: 0.5rem;
    border-radius: 0.2rem;
  }

  .tab__item:last-child {
    background-color: #ff3e00;
    color: var(--white);
    margin-left: auto;
  }

  .tab__item:hover {
    cursor: pointer;
  }

  .tab__item-checked {
    background-color: var(--dark);
    color: var(--white);
  }

  /* Content */
  .content {
    margin-top: 0.5rem;
  }

  .content__item {
    display: none;
  }

  .content__item-active {
    display: block;
  }
</style>
