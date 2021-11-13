<div class="container">
    <nav>
        <a href="/">home</a>
        <a href="/pages/about">about</a>
        <a href="/pages/vowel-counter">vowel counter</a>
    </nav>
</div>

<style>
    :global(body) {
        background: linear-gradient(0.25turn, #e66465, #9198e5);
        font-family: Helvetica, sans-serif;
    }
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
    .container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 90vh;
    }
</style>
