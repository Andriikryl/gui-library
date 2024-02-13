<script lang="ts">
  import { GUI, guiControls } from "$lib/gui";
  import Container from "./Container.svelte";
  import PlayGround from "./PlayGround.svelte";

  const gui = guiControls({
    x: 20,
    y: 20,
    width: 100,
    height: 200,
    size: 4,
  });
</script>

<section>
  <Container>
    <PlayGround>
      <GUI controls={gui} />
      <div class="svg__box">
        <svg width="300" height="300">
          <rect
            x={$gui.x}
            y={$gui.y}
            width={$gui.width}
            height={$gui.height}
            style="stroke: #d90429; fill: none;"
            stroke-width={$gui.size}
          />
        </svg>
      </div>
    </PlayGround>
  </Container>
</section>

<style>
  .svg__box {
    background-color: #ffffff;
    opacity: 0.5;
    background-image: linear-gradient(#000000 1px, transparent 1px),
      linear-gradient(to right, #000000 1px, #ffffff 1px);
    background-size: 20px 20px;
  }
</style>
