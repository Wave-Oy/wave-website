<script lang="ts">

</script>

<nav>
    <div class="container">
        <a href="/" class="logo">wave</a>
        <ul>
            <li>
                <a href="/">About</a>
            </li>
            <li>
                <a href="/">Contact</a>
            </li>
            <li>
                <a href="/">For salons</a>
            </li>
        </ul>
    </div>
</nav>

<style lang="scss">
    nav {
        height: var(--nav-height);
        margin: 0;
        padding: 0;
        background: none;
        background-color: var(--background-white);
        backdrop-filter: blur(100px);
    }
    .logo {
        line-height: var(--nav-height);
        float: left;
        text-decoration: none;
        font-weight: 500;
        color: var(--foreground-accent);
        font-size: 2.6rem;
        letter-spacing: -0.05em;
    }
    ul {
        list-style-type: none;
        float: right;
        margin: 0;
        padding: 0;
    }
    li {
        text-align: center;
        float: left;
        display: block;
        margin-left: 4rem;
        font-weight: 500;
    }
    li a {
        line-height: var(--nav-height);
        text-decoration: none;
        display: block;
        color: var(--foreground-accent);
        font-size: var(--label-medium);
    }
</style>
