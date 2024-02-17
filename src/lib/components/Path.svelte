<script lang="ts">
  import { GUI, guiControls } from "$lib/gui";
  import Container from "./Container.svelte";
  import PlayGround from "./PlayGround.svelte";

  const gui = guiControls({
    pint_1x: 101,
    pint_1Y: 87,
    pint_2x: 411,
    pint_2Y: 603,
    pint_3x: 726,
    pint_3Y: 0,
    stroke_width: 25,
  });
</script>

<section class="section">
  <Container>
    <p class="text">
      The SVG poligon element defines a closed polygon. The points attribute
      defines a series of x,y values for each point in the polygon.
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
          <path
            d="M 50 400 Q {$gui.pint_1x} {$gui.pint_1Y} 250 400 Q {$gui.pint_2x} {$gui.pint_2Y} 550 400 Q {$gui.pint_3x} {$gui.pint_3Y} 750 400"
            fill="none"
            stroke="black"
            stroke-width="23"
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
