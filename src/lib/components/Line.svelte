<script lang="ts">
  import { GUI, guiControls } from "$lib/gui";
  import Container from "./Container.svelte";
  import PlayGround from "./PlayGround.svelte";

  const gui = guiControls({
    x1: 50,
    y1: 300,
    x2: 375,
    y2: 50,
    stroke_width: 25,
  });
</script>

<section class="section">
  <Container>
    <p class="text">
      The SVG line element defines a line. The attributes are x1 & y1 for the
      horizontal and vertical position of the starting point and x2 & y2 for the
      horizontal and vertical position of the ending point of the line.
    </p>
    <PlayGround>
      <GUI controls={gui} />
      <div class="svg__box">
        <svg
          width="300"
          height="300"
          viewBox="0 0 800 800"
          xmlns="http://www.w3.org/2000/svg"
        >
          <line
            x1={$gui.x1}
            y1={$gui.y1}
            x2={$gui.x2}
            y2={$gui.y2}
            stroke="black"
            stroke-width={$gui.stroke_width}
          />
        </svg>
      </div>
    </PlayGround>
  </Container>
</section>

<style>
  .section {
    margin-block: 20px;
  }
</style>
