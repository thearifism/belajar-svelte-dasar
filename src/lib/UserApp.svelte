<script>
  import UserRow from "./UserRow.svelte";

  const user = {
    id: 1,
    name: "Eko",
    address: "Jakarta",
  };
</script>

<table>
  <thead>
    <tr>
      <th>Id</th>
      <th>Name</th>
      <th>Address</th>
    </tr>
  </thead>
  <tbody>
    <UserRow {...user} />
  </tbody>
</table>
