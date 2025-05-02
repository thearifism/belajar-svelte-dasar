<script>
  let { id, name, onedit } = $props();

  function save() {
    onedit(id, name);
  }
</script>

{id} <input type="text" {id} bind:value={name} />
<button onclick={save}>Save</button>
