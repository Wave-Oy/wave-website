<script lang="ts">
    import { base } from '$app/paths';
    import {page, navigating} from '$app/stores';

    let pagesChecked = false;
    let currentRoute: string = '/';

    function resetNavbar () {
        pagesChecked = false;
    }

    function getPage() {
        if ($navigating) {
            currentRoute = $navigating.to.url.pathname.split('/')[1].toLowerCase();
        } else {
            currentRoute = $page.url.pathname.split('/')[1].toLowerCase();
        }
    }

    $: if ($navigating) {
        resetNavbar();
        getPage();
    }

    getPage();
</script>

<nav>
    <div class="container">
        <a href="{base}/" class="logo">wave</a>

        <!-- Burger menu -->
        <input type="checkbox" id="pages-input" bind:checked={pagesChecked}>
        <label for="pages-input" id="pages-button">
            <div class="bar1"></div>
            <div class="bar2"></div>
            <div class="bar3"></div>
        </label>

        <!-- Pages -->
        <ul>
            <li>
                <a href="{base}/about" class:active-route={currentRoute=="about"}>About</a>
            </li>
            <li>
                <a href="{base}/forbusinesses" class:active-route={currentRoute=="forbusinesses"}>For Businesses</a>
            </li>
            <li>
                <a href="{base}/" class:active-route={currentRoute=="contact"}>Contact Us</a>
            </li>
        </ul>
    </div>
</nav>

<style lang="scss">
    nav {
        position: fixed;
        z-index: 1;
        width: 100%;
        height: var(--nav-height);
        margin: 0;
        padding: 0;
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
        display: block;
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
        font-size: var(--label-small);
        font-weight: 500;
    }
    .active-route {
        font-weight: 600;
    }
    #pages-button {
        display: none;
        height: var(--nav-height);
        width: 30px;
        padding: 1.5em 0;
        float: right;
        cursor: pointer;
    }
    #pages-input {
        display: none;
    }
    .bar1, .bar2, .bar3 {
        width: 100%;
        height: 3px;
        background-color: var(--foreground-accent);
        margin: 5px 0;
        transition: 0.1s;
        border-radius: 2px;
    }
    /* Responsive view */
    @media (max-width: 1000px) {
        ul {
            visibility: hidden;
            padding-top: var(--nav-height);
            height: 200vh;
            opacity: 0;
            position: fixed;
            left: 0;
            width: 100%;
            background-color: var(--background-primary);
        }
        li {
            float: none;
            text-align: left;
            margin: 0;
            padding: 5px var(--container-padding) 5px var(--container-padding);
            border-bottom: 1px solid var(--foreground-accent);
        }
        li a {
            width: 100%;
            line-height: 50px;
            font-size: var(--label-medium);
        }
        #pages-button {
            position: static;
            display: block;
            margin-left: 10px;
        }
        /* Logic for mobile menu */
        #pages-input:checked ~ ul {
            visibility: visible;
            opacity: 1;
            transition: opacity .2s, visibility .2s;
        }
        #pages-input:checked ~ #pages-button {
            position: relative;
            z-index: 2;
        }

        /* Rotate bars */
        #pages-input:checked ~ #pages-button > .bar1 {
            transform: translate(0, 8px) rotate(-45deg);
        }
        #pages-input:checked ~ #pages-button > .bar2 {
            opacity: 0;
        }
        #pages-input:checked ~ #pages-button > .bar3 {
            transform: translate(0, -8px) rotate(45deg);
        }
    }
</style>
