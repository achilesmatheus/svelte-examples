<script>
  let tasks = ["Learn svelte", "Learn C#"];
  let value = "";

  function addTask(taskName) {
    // Prevent duplicated values
    if (tasks.find((task) => task === taskName)) return;

    // Prevent blank task
    if (taskName.trim().length === 0) return;

    tasks = [...tasks, taskName];
  }

  function removeTask(taskName) {
    tasks = tasks.filter((task) => task !== taskName);
  }
</script>

<label for="task">Task name: </label>
<input bind:value type="text" name="task" />
<button class="btn" on:click={() => addTask(value)}>Add task</button>

<div class="wrapper">
  {#each tasks as task (task)}
    <div class="card" on:click={() => removeTask(task)}>{task}</div>
  {/each}
</div>

<style>
  .wrapper {
    display: flex;
    gap: 1rem;
  }

  .card {
    cursor: pointer;
  }
</style>
