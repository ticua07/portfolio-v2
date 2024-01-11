<script>
    import ConfettiPfp from "../components/ConfettiPFP.svelte";
    import ConfettiWholePage from "../components/ConfettiWholePage.svelte";
    import Icon from "../components/Icon.svelte";
</script>

<div class="container">
    <ConfettiWholePage />
    <div class="portfolio">
        <!-- <img class="image" src="./cat.png" alt="Nerd cat with glasses" /> -->
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
        height: 100%;
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
    .image {
        height: 400px;
        width: 400px;
        pointer-events: none;
        /* make it undraggable */
        user-select: none;
        -moz-user-select: none;
        -webkit-user-drag: none;
        -webkit-user-select: none;
        -ms-user-select: none;
        pointer-events: none;
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
