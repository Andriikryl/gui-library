<script lang="ts">
  import { GUI, guiControls } from "$lib/gui";

  const gui = guiControls({
    x: 200,
    y: 200,
    radius: 100,
    color: "#17191c",
    stroke: "#00ffcc",
    size: 4,
    dash: { value: 0, min: 0, max: 1.1, step: 0.01 },
    offset: { value: 0, min: 0, max: 1.1, step: 0.01 },
  });
</script>

<section>
  <div class="box">
    <GUI controls={gui} />

    <div class="svg__box">
      <svg width="800" height="800" viewBox="0 0 400 400">
        <circle
          cx={$gui.x}
          cy={$gui.y}
          r={$gui.radius}
          fill={$gui.color}
          stroke={$gui.stroke}
          stroke-width={$gui.size}
          stroke-dasharray={$gui.dash.value}
          stroke-dashoffset={$gui.offset.value}
          pathLength="1"
        />
      </svg>
    </div>
  </div>
</section>

<style>
  .box {
    display: flex;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
    font-family: "Manrope", sans-serif;
    color: hsl(220 10% 98%);
  }
  .svg__box {
    background-color: #ffffff;
    opacity: 0.5;
    background-image: linear-gradient(#000000 1px, transparent 1px),
      linear-gradient(to right, #000000 1px, #ffffff 1px);
    background-size: 20px 20px;
  }
</style>
