<div class="box">
  <slot />
</div>

<style>
  .box {
    display: flex;
    justify-content: center;
    padding-block: 20px;
    gap: 20px;
    flex-wrap: wrap;
    font-family: "Manrope", sans-serif;
    color: hsl(220 10% 98%);
    box-shadow:
      0 1px 1px rgba(0, 0, 0, 0.25),
      0 2px 2px rgba(0, 0, 0, 0.2),
      0 4px 4px rgba(0, 0, 0, 0.15),
      0 8px 8px rgba(0, 0, 0, 0.1),
      0 16px 16px rgba(0, 0, 0, 0.05);
  }
</style>
