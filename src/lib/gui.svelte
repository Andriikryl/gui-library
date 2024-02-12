<script lang="ts">
  export let controls;
  const entries: any = Object.entries($controls);
  const isNotEmpty = entries.length > 0;

  const is = {
    number: (value: any) => typeof value === "number",
    boolean: (value: any) => typeof value === "boolean",
    text: (value: any) => typeof value === "string" && !value.startsWith("#"),
    color: (value: any) => typeof value === "string" && value.startsWith("#"),
    range: (value: any) => typeof value === "object",
  };
</script>

{#if isNotEmpty}
  <div class="gui">
    {#each entries as [label, value]}
      <!-- ... -->
    {/each}
  </div>
{/if}
