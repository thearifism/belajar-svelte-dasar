<script>
  import { fade, fly } from "svelte/transition";
  import EditTodo from "./EditTodo.svelte";
  import Todo from "./Todo.svelte";

  let data = $state([]);
  let name = $state("");

  let id = 0;

  function add(e) {
    e.preventDefault();

    data.push({
      id: id++,
      name: name,
    });
    name = "";
  }

  function edit(id) {
    for (let i = 0; i < data.length; i++) {
      if (data[i].id === id) {
        data[i] = { ...data[i], edit: true };
      }
    }
  }

  function onEdit(id, name) {
    for (let i = 0; i < data.length; i++) {
      if (data[i].id === id) {
        data[i] = { ...data[i], name, edit: false };
      }
    }
  }

  function remove(id) {
    data = data.filter((item) => item.id !== id);
  }
</script>

<form>
  <input type="text" id="todo" bind:value={name} />
  <button onclick={add}>Add</button>
</form>

<ul>
  {#each data as todo (todo.id)}
    <li
      in:fly={{ y: -200, duration: 2000 }}
      out:fly={{ y: 200, duration: 2000 }}
      onintrostart={() => console.log("intro started")}
      onintroend={() => console.log("intro ended")}
      onoutrostart={() => console.log("outro started")}
      onoutroend={() => console.log("outro ended")}
    >
      {#if todo.edit}
        <EditTodo id={todo.id} name={todo.name} onedit={onEdit} />
      {:else}
        <Todo {...todo} />
        <button onclick={() => edit(todo.id)}>Edit</button>
        <button onclick={() => remove(todo.id)}>Remove</button>
      {/if}
    </li>
  {/each}
</ul>

<style>
  :global {
    button {
      background-color: #4caf50; /* Green */
      border: none;
      color: white;
      padding: 10px 20px;
      text-align: center;
      text-decoration: none;
      display: inline-block;
      font-size: 16px;
      margin: 4px 2px;
      cursor: pointer;
      border-radius: 5px;
      transition: background-color 0.3s ease;
    }

    button:hover {
      background-color: #45a049; /* Darker green */
    }
  }
</style>
