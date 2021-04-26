<script>
  import Todos from "./Todos.svelte";

  let todos = {
    todo: [],
    doing: [],
    done: [],
  };
</script>

<main>
  <Todos bind:todos />
</main>

<style>
  main {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
    margin: 0;
    padding: 0;
    text-align: center;
    background-color: #e7e7e7;
    /* background: rgb(123, 0, 255);
    background: linear-gradient(
      180deg,
      rgba(123, 0, 255, 1) 0%,
      rgba(148, 0, 255, 1) 50%,
      rgba(231, 0, 255, 1) 100%
    ); */
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
