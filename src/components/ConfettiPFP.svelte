<script lang="ts">
  // @ts-nocheck

  import { Confetti } from "svelte-confetti";

  const duration = 2000;

  let things = [];
  let timeout;
  const transColors = ["#5BCEFA", "#F5A9B8", "#FFFFFF"];

  async function moveConfetti(event) {
    const { target, clientX, clientY } = event;

    const elementY = target.getBoundingClientRect().top;
    const elementX = target.getBoundingClientRect().left;

    const x = clientX - elementX;
    const y = clientY - elementY;

    things = [...things, { x, y }];

    clearTimeout(timeout);

    timeout = setTimeout(() => (things = []), duration);
  }
</script>

<!-- svelte-ignore a11y-no-static-element-interactions -->
<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
<div class="box" on:click={moveConfetti}>
  <picture>
    <!-- Check if the browser supports AVIF, if yes, use AVIF -->
    <source srcset="cat.avif" type="image/avif" />
    <!-- If AVIF is not supported, fallback to PNG -->
    <source srcset="cat.png" type="image/png" />
    <!-- Fallback for browsers that do not support the <picture> element -->
    <img src="cat.png" alt="Nerd cat with glasses" />
  </picture>
  {#each things as thing}
    <div class="mover" style="left: {thing.x}px; top: {thing.y}px">
      <Confetti
        colorArray={transColors}
        y={[-0.6, 0.6]}
        x={[-0.6, 0.6]}
        amount={20}
        duration={2000}
        fallDistance="5vh"
      />
    </div>
  {/each}
</div>

<style>
  .box {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    max-height: 400px;
    max-width: 400px;
    min-height: 200px;
    min-width: 200px;
    border-radius: 0.5rem;
    user-select: none;
    /* make it undraggable */
    user-select: none;
    -moz-user-select: none;
    -webkit-user-drag: none;
    -webkit-user-select: none;
    -ms-user-select: none;
  }

  .box img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .mover {
    position: absolute;
  }
</style>
