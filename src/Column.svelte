<script>
  import AddTodo from "./AddTodo.svelte";
  import Todo from "./Todo.svelte";
  export let todos;
  export let type;
</script>

<article>
  <p>{type.toUpperCase()}</p>
  {#each todos[type] as todo}
    <Todo bind:todos {todo} {type} />
  {/each}
  {#if type === "todo"}
    <AddTodo bind:todos {type} />
  {/if}
</article>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Roboto:wght@300&display=swap");
  article {
    height: 100%;
    width: 100%;
    display: flex;
    align-items: center;
    flex-direction: column;
    border-radius: 36px;
    color: rgb(0, 0, 32);
    background: #e0e0e0;
    box-shadow: 9px 9px 19px #929292, -9px -9px 19px #ffffff;
    font-family: "Roboto", sans-serif;
    font-weight: bold;
    font-size: 1.4em;
  }
</style>
