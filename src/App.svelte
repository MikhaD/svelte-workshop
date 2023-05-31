<script lang="ts">
  import Card from "./lib/Card.svelte";

  let toDo = "";
  let toDos = ["Learn Svelte"];

  function addToDo() {
    if (toDo === "") return;
    toDos.push(toDo);
    toDos = toDos;
    toDo = "";
  }
</script>

<h1>To Do List</h1>
<div class="inputs">
  <input
    type="text"
    bind:value={toDo}
    on:keypress={(e) => {
      if (e.key === "Enter") addToDo();
    }}
  />
  <button on:click={addToDo}>Add</button>
</div>
<div class="list" />
{#each toDos as toDo}
  <Card text={toDo} />
{/each}

<style lang="scss">
  .inputs {
    display: flex;
    gap: 1em;
    margin-bottom: 1em;
  }
  input {
    flex: 1;
  }
  button {
    width: 6em;
  }
</style>
