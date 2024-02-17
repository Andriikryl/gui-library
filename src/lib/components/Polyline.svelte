<script lang="ts">
  import { GUI, guiControls } from "$lib/gui";
  import Container from "./Container.svelte";
  import PlayGround from "./PlayGround.svelte";

  const gui = guiControls({
    pint_1x: 193,
    pint_1Y: 87,
    pint_2x: 472,
    pint_2Y: 356,
    pint_3x: 177,
    pint_3Y: 568,
    stroke_width: 25,
  });
</script>

<section class="section">
  <Container>
    <p class="text">
      The SVG poliline element defines an open shape made up of a series of
      lines. The points attribute defines a series of x,y values for each point
      in the polyline.
    </p>
    <PlayGround>
      <GUI controls={gui} />
      <div class="svg__box">
        <svg
          viewBox="0 0 800 800"
          xmlns="http://www.w3.org/2000/svg"
          width="300"
          height="300"
        >
          <polyline
            points="{$gui.pint_1x},{$gui.pint_1Y} {$gui.pint_2x},{$gui.pint_2Y} {$gui.pint_3x},{$gui.pint_3Y}"
            fill="none"
            stroke="black"
            stroke-width="20"
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
