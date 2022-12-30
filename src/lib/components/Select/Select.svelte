<script>
  import { options } from "./options";
</script>

<div class="wrapper">
  <label for="code-snippet">Select snippet:</label>
  <select on:change name="code-snippet">
    {#each options as { text, value }}
      <option {value}>{text}</option>
    {/each}
  </select>
</div>

<style>
  .wrapper {
    margin: 1rem 0;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1rem;
  }

  .wrapper select {
    min-width: 150px;
    background-color: var(--white);
    border: none;
    padding: 0.5rem;
    border-radius: 0.2rem;
    outline: none;
    box-shadow: rgba(60, 64, 67, 0.15) 0px 2px 2px 0px,
      #ffffff26 0px 1px 3px 1px;
  }
</style>
