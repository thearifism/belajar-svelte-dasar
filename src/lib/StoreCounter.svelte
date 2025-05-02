<script>
  import { counter } from "../state/counter";

  function incremment() {
    $counter++;
  }
</script>

<button onclick={incremment}>Increment : {$counter}</button>
