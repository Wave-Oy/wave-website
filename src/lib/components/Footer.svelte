<script lang="ts">
    import { base } from '$app/paths';
</script>

<footer>
    <div class="container">
        <a href="{base}/" class="logo">wave</a>
        <ul>
            <li>
                <a href="">Sign up to be first to know</a>
            </li>
        </ul>
    </div>
</footer>

<style lang="scss">
    footer {
        position: sticky;
        top: 100%;
        height: 100px;
        margin: 0;
        padding: 0;
        background: none;
        background-color: var(--background-accent);
        backdrop-filter: blur(100px);
    }

    .logo {
        line-height: 100px;
        float: left;
        text-decoration: none;
        font-weight: 500;
        color: var(--foreground-on-accent);
        font-size: 2.6rem;
        letter-spacing: -0.05em;
    }

    ul {
        float: right;
    }

    li {
    }

    li a {
        text-decoration: none;
        display: block;
        color: var(--foreground-accent);
        font-size: var(--label-medium);
    }
</style>
