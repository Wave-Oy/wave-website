<script lang="ts">
    import { base } from '$app/paths';
</script>

<footer>
    <div class="container">
        <div class="content">
            <a href="{base}/" class="logo">wave</a>
            <div class="links">
                <a href="https://www.linkedin.com/company/waveapplication/">LinkedIn</a>
            </div>
        </div>
        <div class="contact">
            <p class="footer-text">Contact us:</p>
            <a href='mailto:contact@waveapp.fi'>contact@waveapp.fi</a>
        </div>
    </div>
</footer>

<style lang="scss">
    footer {
        position: sticky;
        top: 100%;
        height: 100px;
        margin: 0;
        padding: 20px 0 20px 0;
        background: none;
        background-color: var(--background-accent);
        backdrop-filter: blur(100px);
    }

    .content {
        float: left;
    }

    .logo {
        padding: 0;
        margin: 0;
        text-decoration: none;
        font-weight: 500;
        color: var(--foreground-on-accent);
        font-size: 3.6rem;
        letter-spacing: -0.05em;
    }

    .links {
        padding: 0 0 0 0;
        margin: 10px 0 0 0;
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
    }

    .links a {
        text-decoration: none;
        color: var(--foreground-on-accent);
        font-size: var(--label-small);
    }

    .contact {
        padding: 0 0 0 0;
        margin: 0 0 0 0;
        height: 100px;
        float: right;
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
    }

    .contact a {
        text-decoration: none;
        color: var(--foreground-on-accent);
        font-size: var(--label-small);
    }

    .footer-text {
        padding: 0 0 0 0;
        margin: 0 0 10px 0;
        color: var(--foreground-on-accent);
        font-size: var(--label-small);
    }
</style>
