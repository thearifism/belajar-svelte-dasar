<script>
  import Layout from "./Layout.svelte";
</script>

<Layout title="Contoh Blog" footer="Copyright 2025">
  {#snippet content()}
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugiat voluptatum
      esse iusto libero, ipsum porro similique assumenda tempore deleniti ab
      quasi animi odio expedita veniam voluptate velit, totam recusandae
      impedit.
    </p>
    <p>
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. Deleniti rerum
      commodi voluptatem modi consequuntur? Suscipit repudiandae et iusto alias
      dicta officiis ea, provident veniam obcaecati quas. Culpa ad quis
      similique.
    </p>
  {/snippet}
</Layout>
