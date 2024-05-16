<script lang="ts">
    import { base } from '$app/paths';
    import Button from '$lib/components/Button.svelte';
</script>

<div class="page">
    <div class="container">
        <header>
            <div class="row">
                <div>
                    <h1 class="gradient-r-l">More personal experience<br>for your customers</h1>
                    <p>Wave serves as an easy-to-use tool to attract new customers, and enhance customer satisfaction!</p>
                    <a href={`${base}/contact`} style="margin-bottom: 1rem;"><Button text="Contact us" shape="rectangle" size="medium" layout="label" color="accent" disabled={false}/></a>
                </div>
            </div>
        </header>


        <div class="col main-section">
            <div class="row">
                <div class="col box-around first-box" style="margin-top: 0;">
                    <h2 class="gradient-l-r">Know what your customers want</h2>
                    <p>Wave gives you a clear idea what kind of a haircut your customers want. Waves personal hairstyle asssitant matches your customers with the most fitting hairstyles possible. With wave, you will never have a situation where the customer wants somethingh impossible.</p>
                </div>
                <div class="col" style="margin-top: 25px;">
                    <img src={`${base}/about-decorations.png`} alt="decorations" class="decorations">
                </div>
            </div>

            <div class="col box-around second-box">
                <h2 class="gradient-l-r">Give your customers the products they need</h2>
                <p>Wave matches your customers directly with the products they need in the app. Wave suggests different kinds of products most suitable for your customers providing personalized recommendations thus increasing sales. In fact, 3 out of 4 customers are more likely to purchase personalized product recommendations.</p>
            </div>

            <div class="row">
                <div class="col" style="margin-bottom: 100px;">
                    <img src={`${base}/about-decorations.png`} alt="decorations" class="decorations">
                </div>
                <div class="col box-around third-box">
                    <h2 class="gradient-l-r">All this in an easy integration</h2>
                    <p>Wave is shortly going to be available as an easy to integrate solution for all kinds of businesses! Contact us to hear more about our solutions and to discuss about integration and testing.</p>
                </div>
            </div>
        </div>
    </div>
</div>

<style lang="scss">
    header {
            padding: 80px 0 50px 0;
            transition: padding 0.3s;
    }
    header h1 {
        font-size: var(--header-xlarge);
        min-width: 55rem;
        line-height: 7rem;
        font-weight: 600;
        margin: 0 0 25px 0;
        padding: 0;
        min-width: 61rem;
    }

    header p {
        font-size: var(--paragraph-medium);
        color: var(--foreground-accent);
        font-weight: 500;
        margin: 0 0 25px 0;
        max-width: 500px;
        padding: 0;
    }

    .gradient-l-r {
        background: linear-gradient(to right, var(--blue-800), #4585E5, var(--blue-700));
        background-clip: text;
        color: rgba(0,0,0,0);
    }

    .gradient-r-l {
        background: linear-gradient(to right, var(--blue-700), #4585E5, var(--blue-800));
        background-clip: text;
        color: rgba(0,0,0,0);
    }

    .box-around {
        background-color: var(--blue-100);
        // padding: 20px 40px 20px 40px;
        padding: 40px;
        border-radius: 20px;
        margin-top: 100px;
        max-width: 900px;
        height: 100%;

        &.first-box {
            margin-top: 0;
        }

        &.second-box {
            margin: 0;

            @media (max-width: 1000px) {
                margin-top: 50px;
            }

            @media (max-width: 600px) {
                margin-top: 50px;
            }
        }

        &.third-box {
            margin-top: 150px;

            @media (max-width: 1000px) {
                margin-top: 50px;

                margin-bottom: 50px;
            }

            @media (max-width: 600px) {
                margin-top: 50px;
                margin-bottom: 50px;
            }
        }
    }

    h1 {
        font-size: var(--header-large);
        font-weight: 600;
        margin: 0;
        padding: 0;

        &.section-title {
            font-size: 4.8rem;
            margin-top: 2rem;
        }

        &.margin-bottom {
            margin-bottom: 2rem;
        }
    }

    h2 {
        font-size: var(--header-medium);
        font-weight: 600;
        margin: 0;
        padding: 0;

        &.section-title {
            font-size: 4.8rem;
            margin-top: 2rem;
        }

        &.margin-bottom {
            margin-bottom: 2rem;
        }
    }

    p {
        font-size: var(--paragraph-medium);
        color: var(--foreground-accent);
        font-weight: 500;
        padding: 0;
    }

    .row {
        display: flex;
        flex-direction: row;
    }

    .col {
        display: flex;
        flex-direction: column;

        &.margin {
            margin: 3rem;
        }

        &.main-section {
            margin-top: 100px;
            justify-content: center;
            align-items: center;

            @media (max-width: 1000px) {
                margin-top: 50px;
            }

            @media (max-width: 600px) {
                margin-top: 50px;
            }
        }

    }

    .decorations {
        display: block;
    }

    @media (max-width: 1000px) {
        header h1 {
            min-width: 55vw;
            font-size: 6vw;
            line-height: 7vw;
        }
        header img {
            overflow: hidden;
            margin-right: 0;
        }
        .main-content {
            align-items: flex-start;
        }
        .main-content h2 {
        }
        .main-content p {
            text-align: left;
        }
        header p {
            max-width: 18em;
        }
        .decorations {
            display: none;
        }
    }

    @media (max-width: 800px) {
        header h1 {
            font-size: var(--header-large);
            min-width: 45rem;
            line-height: 5.4rem;
        }
    }

    @media (max-width: 600px) {
        header h1 {
            font-size: 10vw;
            min-width: 0;
            width: 95vw;
            line-height: 12vw;
        }
        header {
            padding: 40px 0 50px 0;
        }
        header img {
            display: none;
        }
        .main-content h2 {
            font-size: var(--header-medium);
        }

        .decorations {
            display: none;
        }
    }
</style>