<div class="wrapper bui">
    <nav>
        <a href="/">Start</a>
        <a href="/button">Button</a>
    </nav>
    <main>
        <slot />
    </main>
</div>

<script>
    import '$lib/styles/default.css'
</script>

<style>
    :global(body, html){
        padding: 0;
        margin: 0;
        height: 100%;
    }

    .wrapper {
        background: var(--background);
        min-height: 100vh;

        display: flex;

    }

    nav {
        flex: 0 1;
        background: var(--surface-alternative);
        display: flex;
        flex-direction: column;
        gap: 10px;
        padding: 30px;
    }
</style>