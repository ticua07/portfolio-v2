<script lang="ts">
    import { page } from "$app/stores";
</script>

<div class="container">
    <img
        src="https://http.cat/images/{$page.status}.jpg"
        alt="HTTP Error with a meme cat"
    />
    <h1>{$page.status} - {$page.error?.message}</h1>
    <h1><a href="/">Go back home</a></h1>
</div>

<style>
    @import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap");

    .container {
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        background-color: #141414;
    }

    a {
        color: #fff;
        font-style: italic;
    }

    h1 {
        color: #fff;
        font-size: 48px;
    }

    h1 {
        font-family: "Inter";
    }
</style>
