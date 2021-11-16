<script lang="ts">
    import Button, { Label } from "@smui/button";

    let lightTheme =
        typeof window === "undefined" ||
        window.matchMedia("(prefers-color-scheme: light)").matches;

    function switchTheme() {
        lightTheme = !lightTheme;
        let themeLink = document.head.querySelector<HTMLLinkElement>("#theme");
        if (!themeLink) {
            themeLink = document.createElement("link");
            themeLink.rel = "stylesheet";
            themeLink.id = "theme";
        }
        themeLink.href = `/smui${lightTheme ? "" : "-dark"}.css`;
        document.head
            .querySelector<HTMLLinkElement>('link[href="/smui-dark.css"]')
            ?.insertAdjacentElement("afterend", themeLink);
    }
</script>

<div class="container">
    <nav>
        <a href="/">home</a>
        <a href="/pages/about">about</a>
        <a href="/pages/vowel-counter">vowel counter</a>
    </nav>
    <Button on:click={switchTheme}>
        <Label>{lightTheme ? "Lights off" : "Lights on"}</Label>
    </Button>
</div>

<style>
    .container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 90vh;
    }
</style>
