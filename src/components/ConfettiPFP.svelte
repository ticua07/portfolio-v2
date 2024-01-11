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
    <img
        src="cat.png"
        class="box"
        alt="Nerd cat with glasses"
        on:click={moveConfetti}
    />
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
        background-image: "./cat.png";
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

    .mover {
        position: absolute;
    }
</style>
