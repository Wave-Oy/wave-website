<script lang="ts">
    // For icons check: https://svelte-icons.vercel.app/
    import { base } from '$app/paths';
    import Button from "$lib/components/Button.svelte";
    import Page from './about/+page.svelte';
    import axios from 'axios';

    const handleClick = () => {
        console.log("Button clicked");
        sendEmail()
    }

    const sendEmail = async () => {
        const payload = {
            Messages: [
            {
                From: {
                Email: 'wavebot@waveapp.fi',
                Name: 'Wave Bot'
                },
                To: [
                {
                    Email: 'georgy@waveapp.fi',
                    Name: 'Georgy'
                }
                ],
                Subject: 'Your email flight plan!',
                TextPart: 'Dear passenger 1, welcome to Mailjet! May the delivery force be with you!',
                HTMLPart: '<h3>Dear passenger 1, welcome to <a href="https://www.mailjet.com/">Mailjet</a>!</h3><br />May the delivery force be with you!'
            }
            ]
        };

        try {
            const response = await axios.post(
            'https://api.mailjet.com/v3.1/send',
            payload,
            {
                auth: {
                    username: process.env.MAILJET_API_KEY,
                    password: process.env.MAILJET_SECRET_KEY
                },
                headers: {
                    'Content-Type': 'application/json',
                    'Access-Control-Allow-Methods': 'GET, POST, PUT, DELETE, PATCH, OPTIONS',
                    'Access-Control-Allow-Origin': '*',
                    'Access-Control-Allow-Headers': '*',
                }
            }
            );

            console.log('Email sent successfully:', response.data);
        } catch (error) {
            console.error('Error sending email:', error);
        }
    };


</script>

<div class="home page">
    <div class="container">
        <header>
            <div class="row">
                <div>
                    <h1 class="gradient-r-l">Choosing a hairstyle<br>has never been<br>easier</h1>
                    <p>Wave is transforming the way you choose and book your hairstyle with just a selfie.</p>
                    <Button handler={handleClick} text="Sign up for testing" shape="rectangle" size="large" layout="label" color="accent" disabled={false}/>
                </div>
                <div>
                    <img src={`${base}/design-preview.png`} alt="Design Preview" />
                </div>
            </div>
        </header>
        <section class="main-content">
            <h2 class="gradient-r-l">An interactive reservation system</h2>
            <p>Wave offers a reservation system equipped with a personal hairstyle assistant, to help people choose haircuts based on real data and communicate it to salons.</p>
        </section>
        <section class="parallax-content">
            <div class="row">
                <div class="col margin">
                    <h3>Take a selfie</h3>
                    <img class="bottom-fade" src={`${base}/take-selfie.png`} alt="Take a selfie" />
                </div>
                <div class="col margin">
                    <h3>Choose a style</h3>
                    <img class="bottom-fade" src={`${base}/select-style.png`} alt="Select a style" />
                </div>
                <div class="col margin">
                    <h3>Book a time</h3>
                    <img class="bottom-fade" src={`${base}/book-time.png`} alt="Book a time" />
                </div>
        </section>
    </div>
</div>

<style lang="scss">
    header h1 {
        font-size: var(--header-xlarge);
        line-height: 7rem;
        font-weight: 600;
        margin: 0 0 25px 0;
        padding: 0;
    }

    header p {
        font-size: var(--paragraph-medium);
        color: var(--foreground-accent);
        font-weight: 500;
        margin: 0 0 50px 0;
        max-width: 500px;
        padding: 0;
    }

    .main-content {
        padding-top: 100px;
        padding-bottom: 100px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
    }
    .main-content h2 {
        font-size: var(--header-large);
        font-weight: 600;
        margin: 0 0 25px 0;
        padding: 0;
    }
    .main-content p {
        font-size: var(--paragraph-medium);
        color: var(--foreground-accent);
        text-align: center;
        max-width: 800px;
        font-weight: 600;
        margin: 0;
        padding: 0;
    }

    .parallax-content {

    }
    .parallax-content h3 {
        font-size: var(--header-small);
        color: var(--foreground-accent);
        font-weight: 600;
        margin: 0 0 25px 0;
        padding: 0;
    }

    .row {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }

    .col {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        &.margin {
            margin: 3rem;
        }
    }

    h1 {
        font-size: 3.6rem;
        font-weight: 500;
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

    .bottom-fade {
        mask-image: linear-gradient(to bottom, rgba(0,0,0,1), rgba(0,0,0,1), rgba(0,0,0,1), rgba(0,0,0,0));
        mask-size: 100% 90%;
        mask-repeat: no-repeat;
        mask-position: left top, left bottom;
    }

    .arrow-down {
        margin-bottom: 4rem;
        width: 5rem;

        // Doesn't work
        background: linear-gradient(to right, var(--blue-700), #4585E5, var(--blue-800));
        background-clip: text;
        color: rgba(0,0,0,0);

        color: var(--blue-700);
    }
</style>
