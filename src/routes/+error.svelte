<script>
    import { page } from "$app/stores";
</script>

<div class="container">
    <h1>{$page.status} - {$page.error?.message}</h1>
    <h1><a href="/">Go back home</a></h1>
</div>

<style>
    @import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap");

    .container {
        height: 100%;
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
