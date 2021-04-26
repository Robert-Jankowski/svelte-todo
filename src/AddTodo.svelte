<script>
  import { v4 as uuidv4 } from "uuid";
  export let todos;
  export let type;

  let input = "";

  const onKeyPress = (e) => {
    if (e.charCode === 13) {
      todos = {
        ...todos,
        [type]: [
          ...todos[type],
          {
            id: uuidv4(),
            text: input.value,
          },
        ],
      };
      input.value = "";
    }
  };
</script>

<input
  type="text"
  bind:this={input}
  on:keypress={onKeyPress}
  placeholder="Type your todo and hit Enter"
/>

<style>
  input {
    background-color: transparent;
    border: none;
    border-bottom: 1px solid black;
    height: 10%;
    width: 80%;
  }
</style>
