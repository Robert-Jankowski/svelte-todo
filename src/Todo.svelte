<script>
  export let todos;
  export let todo;
  export let type;

  const onClick = () => {
    todos = {
      ...todos,
      [type]: todos[type].filter((next) => next.id !== todo.id),
    };
    if (type === "todo") {
      todos = {
        ...todos,
        doing: [...todos.doing, todo],
      };
    } else if (type === "doing") {
      todos = {
        ...todos,
        done: [...todos.done, todo],
      };
    } else {
      todos = {
        ...todos,
        todo: [...todos.todo, todo],
      };
    }
  };

  const onDelete = () => {
    todos = {
      ...todos,
      [type]: todos[type].filter((next) => next.id !== todo.id),
    };
  };
</script>

<div on:click={onClick}>
  {todo.text}
  {#if type === "done"}
    <span on:click={onDelete}>
      <img src="deleteicon.svg" alt="delete" />
    </span>
  {/if}
</div>

<style>
  @import url("https://fonts.googleapis.com/icon?family=Material+Icons");
  div {
    background-color: white;
    height: 10%;
    width: 80%;
    overflow-wrap: anywhere;
    border-radius: 12px;
    margin-bottom: 4%;
    padding-left: 5%;
    padding-right: 5%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: black;
    font-weight: normal;
    -webkit-box-shadow: 5px 5px 14px -1px rgba(0, 0, 0, 0.69);
    box-shadow: 5px 5px 14px -1px rgba(0, 0, 0, 0.69);
  }
  span {
    background-color: rgb(148, 0, 0);
    width: 35px;
    height: 35px;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
