<script lang="ts">
    export let url: string;
    export let src: string;
    export let alt: string;
</script>

<a href={url}>
    <img {src} srcset={src} {alt} />
</a>

<style>
    img {
        width: 64px;
        height: 64px;
        opacity: 50%;
        transition: opacity 0.2s;
    }
    img:hover {
        opacity: 1;
    }
</style>
