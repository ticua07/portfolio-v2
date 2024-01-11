<script>
    import Confetti from "svelte-confetti";
</script>

<div
    style="
 position: fixed;
 top: -50px;
 left: 0;
 height: 100vh;
 width: 100vw;
 display: flex;
 justify-content: center;
 overflow: hidden;
 pointer-events: none;"
>
    <Confetti
        x={[-5, 5]}
        colorArray={["#5BCEFA", "#F5A9B8", "#FFFFFF"]}
        y={[0, 0.1]}
        delay={[0, 500]}
        duration={1500}
        amount={300}
        fallDistance="100vh"
    />
</div>
