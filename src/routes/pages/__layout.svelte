<nav>
    <a href="/">home</a>
    <a href="/pages/about">about</a>
    <a href="/pages/vowel-counter">vowel counter</a>
</nav>
<slot />

<style>
    a {
        color: white;
        font-size: 2em;
        margin-right: 10px;
        padding: 10px;
    }
    a:hover {
        color: cyan;
        text-decoration: underline;
        text-decoration-thickness: 5px;
    }
    a:active {
        color: black;
        background-color: white;
        text-decoration: underline;
        text-decoration-thickness: 5px;
    }
    nav > * {
        text-decoration: none;
    }
</style>
