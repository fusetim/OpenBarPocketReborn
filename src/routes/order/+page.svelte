<script lang="ts">
</script>

<div id="container">
    <nav>
        <a href="/order/1">1</a>
        <a href="/order/2">2</a>
        <a href="/order/3">3</a>
        <a href="/order/4">4</a>
        <a href="/order/5">5</a>
    </nav>
</div>

<style lang="scss">
    #container {
        display: block;
        position: relative;
        height: 100vh;
        width: 100vw;
        overflow: hidden;
    }

    nav {
        position: absolute;
        bottom: 0;
        height: 4rem;
        width: 100%;
        background-color: #f0f0f0;
        border-top: 2px solid map-get($gray, 200);
        margin: 0;
        padding: 0.25rem;

        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
    }
</style>