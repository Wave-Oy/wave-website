<script lang="ts">
    // For icons check: https://svelte-icons.vercel.app/
    import { base } from '$app/paths';
    import Button from "$lib/components/Button.svelte";

    let showForm = false;

    let name: string;
    let email: string;
    let city: string;
    let antibot: string;

    let formSent = false;

    const handleClick = () => {
        showForm = !showForm;
    }

    const submitForm = async () => {
        if (antibot) {
            return;
        }
        const google_form_url = `https://docs.google.com/forms/d/e/1FAIpQLSdeTWpcZgsTbNXSqczGqfwS6zqyYCdgI375_J6z6Rmt1YxPBw/formResponse?&submit=Submit?usp=pp_url&entry.111887972=${name}&entry.1362910400=${email}&entry.533110689=${city}`
        const res = await fetch(google_form_url, {
            method: 'GET',
            mode: 'no-cors',
            headers: {
                'Content-Type': 'application/x-www-form-urlencoded',
            },
        })

        if (res.status != 200) {
            console.error()
        }

        formSent = true;
    }
</script>

<div class="home page">
    <div class="container">
        <header>
            <div class="row">
                <div>
                    <h1 class="gradient-r-l">Getting a haircut<br>has never been<br>easier</h1>
                    <p>Wave is transforming the way you choose and book your hairstyle with just a selfie.</p>
                    <Button handler={handleClick} text="Sign up for testing" shape="rectangle" size="medium" layout="label" color="accent" disabled={false}/>
                </div>
                <div>
                    <img src={`${base}/design-preview.png`} alt="Design Preview" />
                </div>
            </div>
        </header>

        <section id="form-section" class="form-section {showForm ? 'visible' : ''}">
            {#if !formSent}
                <h2 class="gradient-l-r">Sign up for testing</h2>
                <form>
                    <div class="form-row">
                        <div class="form-col">
                            <label for="name">Name</label>
                            <input type="text" id="name" name="name" placeholder="Your name" required bind:value={name}>
                        </div>
                        <div class="form-col">
                            <label for="email">Email</label>
                            <input type="email" id="email" name="email" placeholder="Your email" required bind:value={email}>
                        </div>
                        <div class="form-col">
                            <label for="city">City of Residence</label>
                            <input type="text" id="city" name="city" placeholder="Your city" required bind:value={city}>
                        </div>
                        <!-- Protection from bots -->
                        <input style="visibility: hidden; position:fixed;" bind:value={antibot}>
                    </div>
                    <Button handler={submitForm} text="Sign up" shape="rectangle" size="medium" layout="label" color="accent" disabled={false}/>
                </form>
            {:else}
                <h2 class="gradient-l-r">Thank you!</h2>
                <p>We will send you an email as soon as we release our closed test version of the application.</p>
            {/if}
        </section>

        <section class="main-content">
            <h2 class="gradient-r-l">An interactive reservation system</h2>
            <p>Wave offers a reservation system equipped with a personal hairstyle assistant, to help people choose haircuts based on real data and communicate it to salons.</p>
        </section>

        <section class="parallax-content">
            <div class="parallax-item">
                <h3>Take a selfie</h3>
                <img src={`${base}/take-selfie.png`} alt="Take a selfie" />
            </div>
            <div class="parallax-item">
                <h3>Choose a style</h3>
                <img src={`${base}/select-style.png`} alt="Select a style" />
            </div>
            <div class="parallax-item">
                <h3>Book a time</h3>
                <img src={`${base}/book-time.png`} alt="Book a time" />
            </div>
        </section>
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

    header img {
        overflow: hidden;
        width: auto;
        padding: 0;
        height: 500px;
        margin-right: -100px;
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
   
    /* Make parallax later */
    .parallax-content {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        margin: 50px 0 100px 0;
    }
    .parallax-item {
    }
    .parallax-item h3 {
        font-size: var(--header-medium);
        color: var(--foreground-accent);
        font-weight: 600;
        margin: 0 0 25px 0;
        padding: 0;
        text-align: center;
    }
    .parallax-item img {
        width: 250px;
        height: auto;
        padding: 0 50px 0 50px;
    }
    @media (max-width: 1000px) {
        .parallax-item img {
            width: 200px;
            padding: 0 25px 0 25px;
        }
    }
    @media (max-width: 800px) {
        .parallax-content {
            flex-direction: column;
        }
        .parallax-item {
            margin: 0 0 100px 0;
        }
        .parallax-item h3 {
            margin: 0 0 10px 0;
        }
        .parallax-item img {
            width: 70vw;
            padding: 0;
        }
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

    h2 {
        font-size: 3.6rem;
        font-weight: 500;
        margin: 0;
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

    .form-section {
        background: var(--blue-100);
        box-shadow: #F3F6FE 0px 0px 1px 0px;
        padding: 0px 0 0 0;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        border: solid var(--blue-300);
        border-width: 2px 0;
        box-shadow: inset 0px 5px 10px -5px rgba(0, 0, 0, 0.1), inset 0px -5px 10px -5px rgba(0, 0, 0, 0.1);
        visibility: hidden;
        overflow: hidden;
        height: 0rem;
        transition: height 0.5s, padding 0.5s, visibility 0.5s;

        &.visible {
            visibility: visible;
            height: 15rem;
            padding: 100px 0 100px 0;
        }

        
        p {
            font-size: var(--paragraph-medium);
            color: var(--foreground-accent);
            text-align: center;
            max-width: 700px;
            font-weight: 600;
            margin: 10px 0 0 0;
            padding: 0;
        }

        form {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            max-width: 800px;
            gap: 2rem;
            margin-top: 2rem;

            .form-row {
                display: flex;
                flex-direction: row;
                gap: 3rem;

                .form-col {
                    display: flex;
                    flex-direction: column;
                    justify-content: left;

                    label {
                        font-size: var(--label-small);
                        color: var(--foreground-accent);
                        font-weight: 600;
                        padding: 0;
                    }

                    input {
                        padding: 1rem;
                        font-size: var(--label-medium);
                        color: var(--foreground-accent);
                        font-weight: 600;
                        border: solid var(--blue-200);
                        border-width: 1px;
                        border-radius: 0.5rem;
                        background-color: var(--blue-200);
                    }
                }
            }
        }
    }

    @media (max-width: 1000px) {
        .form-section {
            &.visible {
                visibility: visible;
                height: 30rem;
                padding: 100px 10px 100px 10px;
            }
            form {
                .form-row {
                    flex-direction: column;
                }
            }
        }

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
            padding: 80px 0 50px 0;
        }
        header img {
            display: none;
        }
        .main-content h2 {
            font-size: var(--header-medium);
        }
    }
</style>
