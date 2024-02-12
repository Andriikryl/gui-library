<script lang="ts">
  import Header from "$lib/components/Header.svelte";
  import "../app.css";
</script>

<svelte:head>
  <title>Svelte GUI</title>
</svelte:head>

<Header />
<main>
  <slot />
</main>
