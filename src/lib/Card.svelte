<script lang="ts">
  export let text: string;
  let checked = false;
</script>

<div on:click={() => (checked = !checked)} class:checked>
  <input type="checkbox" bind:checked />
  {text}
</div>

<style lang="scss">
  div {
    background-color: #1a1a1a;
    border-radius: 8px;
    padding: 0.6em 1.2em;
    text-align: left;
    margin-bottom: 0.5em;
  }
  .checked {
    text-decoration: line-through;
    background-color: gray;
  }
</style>
