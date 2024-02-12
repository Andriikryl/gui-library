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
  function updateControls(e: Event) {
    // ...
  }
</script>

{#if isNotEmpty}
  <div class="gui">
    {#each entries as [label, value]}
      {#if is.number(value)}
        <label>
          {label}
          <input
            on:change={updateControls}
            on:wheel={updateControls}
            value={$controls[label]}
            data-key={label}
            type="number"
          />
        </label>
      {/if}

      {#if is.boolean(value)}
        <label>
          {label}
          <input
            on:change={updateControls}
            data-key={label}
            checked={$controls[label]}
            type="checkbox"
          />
        </label>
      {/if}

      {#if is.text(value)}
        <label>
          {label}
          <input
            on:input={updateControls}
            data-key={label}
            value={$controls[label]}
            type="text"
          />
        </label>
      {/if}

      {#if is.range(value)}
        <label>
          {label}
          <input
            on:input={updateControls}
            on:wheel={updateControls}
            data-key={label}
            value={$controls[label].value}
            min={$controls[label].min}
            max={$controls[label].max}
            step={$controls[label].step}
            type="range"
          />
        </label>
      {/if}

      {#if is.color(value)}
        <label>
          {label}
          <input
            on:input={updateControls}
            value={$controls[label]}
            data-key={label}
            type="color"
          />
        </label>
      {/if}
    {/each}
  </div>
{/if}
