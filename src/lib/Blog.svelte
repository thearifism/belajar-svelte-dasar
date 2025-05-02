<script>
  import { onMount } from "svelte";
  import Layout from "./Layout.svelte";

  let blog = $state({
    title: "",
    content: "",
    footer: "",
  });

  onMount(async () => {
    const response = await fetch("/blog.json");
    blog = await response.json();
  });
</script>

<Layout title={blog.title} footer={blog.footer}>
  {#snippet content()}
    {@html blog.content}
  {/snippet}
</Layout>
