<script>
  import { SvelteMap } from "svelte/reactivity";

  const students = new SvelteMap();

  let student = $state("");
  let value = $state("");

  function addStudent() {
    students.set(student, value);
    student = "";
    value = "";
  }
</script>

<div>
  Student : <input type="text" bind:value={student} />
  <br />
  Value : <input type="text" bind:value />
  <br />
  <button onclick={addStudent}>Add Student</button>
</div>

<table>
  <thead>
    <tr>
      <th>Student</th>
      <th>Value</th>
    </tr>
  </thead>
  <tbody>
    {#each students as entry (entry[0])}
      <tr>
        <td>{entry[0]}</td>
        <td>{entry[1]}</td>
      </tr>
    {/each}
  </tbody>
</table>
