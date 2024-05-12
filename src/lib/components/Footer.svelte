<script lang="ts">
    import { base } from '$app/paths';
</script>

<footer>
    <div class="container">
        <a href="{base}/" class="logo">wave</a>
    </div>
    <div class="container">
        <a href="{base}/#form-section">Sign up to be the first to know!</a> <!-- Now navigates to the "Hook section"-->
    </div>
    <div class="container">
        <ul>
            <li>
                <a href="{base}/">About</a>
            </li>
            <li>
                <a href="{base}/">Contact</a>
            </li>
            <li>
                <a href="{base}/">For salons</a>
            </li>
        </ul>
    </div>
</footer>

<style lang="scss">
    footer {
        margin: auto;
        padding: 10px;
        height: auto;
        width: 100vw;
        background-color: var(--background-accent);
        justify-content: center;
        display: flex;
        flex-direction: row;
        position: sticky;
        top: 100%;
    }

    .logo {
        line-height: var(--nav-height);
        float: left;
        text-decoration: none;
        font-weight: 500;
        color: var(--foreground-on-accent);
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
    a {
        line-height: var(--nav-height);
        text-decoration: none;
        display: block;
        color: var(--foreground-on-accent);
        font-size: var(--label-medium);
    }
</style>