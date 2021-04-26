<script>
  import Column from "./Column.svelte";

  export let todos;
</script>

<section>
  <Column bind:todos type="todo" />
  <Column bind:todos type="doing" />
  <Column bind:todos type="done" />
</section>

<style>
  section {
    width: 70%;
    height: 70%;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr;
    gap: 5%;
  }
</style>
