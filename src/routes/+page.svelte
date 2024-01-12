<script lang="ts">
    import { onMount } from "svelte";
    import ConfettiPfp from "../components/ConfettiPFP.svelte";
    import ConfettiWholePage from "../components/ConfettiWholePage.svelte";
    import Icon from "../components/Icon.svelte";
    import ConfettiEasterEgg from "../components/ConfettiEasterEgg.svelte";

    let keys = ["t", "r", "a", "n", "s", "Enter"];
    let temp_pressed: string[] = [];
    let ee_activated = false;

    onMount(() => {
        document.addEventListener("keypress", (event) => {
            temp_pressed.push(event.key.toString());

            // Check if temp_pressed is equal to keys
            if (temp_pressed.join("") === keys.join("")) {
                ee_activated = true;
                temp_pressed = []; // Reset temp_pressed if the sequence is correct
            }
        });
    });
</script>

<svelte:head>
    <title>Ticua's Portfolio</title>
</svelte:head>

<div class="container">
    {#if ee_activated}
        <ConfettiEasterEgg />
    {/if}
    <ConfettiWholePage />
    <div class="portfolio">
        <ConfettiPfp />
        <div class="info-container">
            <div class="text-container">
                <h1>Ticua</h1>
                <h2>
                    Passionate developer who loves
                    <span style="color: #F0DB4F">JavaScript</span>
                    and <span style="color: #e53617">Rust</span>.

                    <br />With knowledge in both front-end and back-end services
                </h2>
            </div>
            <div class="icons">
                <Icon
                    url="https://github.com/ticua07"
                    alt="Github's Logo"
                    src="gh-logo.svg"
                />
                <Icon
                    url="https://discordapp.com/users/448952682611474442"
                    alt="Discord's logo"
                    src="ds-logo.svg"
                />
            </div>
        </div>
    </div>
</div>

<style>
    @import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap");

    .container {
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: #141414;
    }

    .portfolio {
        display: flex;
        flex-direction: row;
        gap: 25px;
    }

    .info-container {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        padding-right: 10px;
    }

    .text-container {
        display: flex;
        flex-direction: column;
        gap: 20px;
    }

    .icons {
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 40px;
    }

    @media (max-width: 830px) {
        .portfolio {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        .text-container {
            justify-self: center;
            align-items: center;
            text-align: center;
        }
        .text-container h2 {
            max-width: 400px;
        }
        .info-container {
            justify-self: center;
            align-items: center;
            gap: 30px;
        }
    }

    h1 {
        color: #fff;
        font-size: 48px;
    }
    h2 {
        font-size: 25px;
        opacity: 93.33%;
        color: #eee;
    }
    h1,
    h2 {
        font-family: "Inter";
    }
</style>
