<script lang="ts">
  import { GUI, guiControls } from "$lib/gui";
  import Container from "./Container.svelte";
  import PlayGround from "./PlayGround.svelte";

  const gui = guiControls({
    x: 70,
    y: 70,
    radius: 50,
    add_Cicle: false,
  });
  const extraGui = guiControls({
    x_first: 55,
    y_first: 80,
    radius_first: 5,
    x_second: 85,
    y_second: 80,
    radius_second: 5,
  });
</script>

<section class="scetion">
  <Container>
    <p class="text">
      We draw the cat's face by adding a element. The element's attributes
      specify the center x-coordinate, center y-coordinate, and radius. The
      (0,0) point is the upper left corner of the picture. x coordinates
      increase as you move horizontally to the right; y coordinates increase as
      you move vertically downwards.
    </p>
    <PlayGround>
      <GUI controls={gui} />
      <div class="svg__box">
        <svg width="300" height="300">
          <title>Cat</title>
          <desc>Stick Figure of a Cat</desc>
          <circle
            cx={$gui.x}
            cy={$gui.y}
            r={$gui.radius}
            style="stroke: black; fill: none"
          />
          {#if $gui.add_Cicle}
            <circle
              cx={$extraGui.x_first}
              cy={$extraGui.y_first}
              r={$extraGui.radius_first}
              stroke="black"
              fill="#339933"
            />
            <circle
              cx={$extraGui.x_second}
              cy={$extraGui.y_second}
              r={$extraGui.radius_second}
              stroke="black"
              fill="#339933"
            />
          {/if}
        </svg>
      </div>
      {#if $gui.add_Cicle}
        <GUI controls={extraGui} />
      {/if}
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
  .scetion {
    margin-block-end: 20px;
  }
  .text {
    padding-inline-start: 10px;
    border-left: 4px solid #ffc300;
    color: var(--black, #1b1b1b);
    font-family: Inter;
    font-size: 24px;
    font-style: normal;
    font-weight: 500;
    line-height: 30px;
    letter-spacing: 1.14px;
    margin-block-end: 20px;
  }
</style>
