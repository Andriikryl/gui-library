<script lang="ts">
  import { GUI, guiControls } from "$lib/gui";
  import Container from "./Container.svelte";
  import PlayGround from "./PlayGround.svelte";

  const gui = guiControls({
    rx: 154,
    ry: 100,
    cx: 400,
    cy: 400,
    stroke_width: 10,
  });
</script>

<section>
  <Container>
    <p class="text">
      The SVG elipse element defines an ellipse. The attributes are rx for the
      horizontal radius, ry for the vertical radius, cx for the horizontal
      center and cy for the vertical center.
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
          <ellipse
            rx={$gui.rx}
            ry={$gui.ry}
            cx={$gui.cx}
            cy={$gui.cy}
            fill="#DB7092"
            stroke="#B82E5A"
            stroke-width={$gui.stroke_width}
          />
        </svg>
      </div>
    </PlayGround>
  </Container>
</section>

<style>
</style>
