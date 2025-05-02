<script>
  import { setContext } from "svelte";
  import ContextCounter from "./ContextCounter.svelte";

  const counter = $state({ count: 0 });

  setContext("counter", counter);
</script>

<ContextCounter />
<ContextCounter />
<ContextCounter />
