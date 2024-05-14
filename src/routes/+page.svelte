<script lang="ts">
    // For icons check: https://svelte-icons.vercel.app/
    import { base } from '$app/paths';
    import FaChevronDown from 'svelte-icons/fa/FaChevronDown.svelte'
    import Button from "$lib/components/Button.svelte";
    import Page from './about/+page.svelte';
    import { Parallax, ParallaxLayer, StickyLayer } from 'svelte-parallax'

    let showForm = false;

    let name: string;
    let email: string;
    let city: string;
    let antibot: string;

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

    }

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

        <section id="form-section" class="form-section {showForm ? 'visible' : ''}">
            <h1 class="gradient-l-r">Sign up for testing</h1>
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
        </section>

        <section class="main-content">
            <h2 class="gradient-r-l">An interactive reservation system</h2>
            <p>Wave offers a reservation system equipped with a personal hairstyle assistant, to help people choose haircuts based on real data and communicate it to salons.</p>
        </section>

        <Parallax sections={3}>
            <ParallaxLayer rate={0} offset={0} span={1} style="background-color: orange;" />
            
            <StickyLayer offset={{top: 0.2, bottom: 1}} let:progress>
                <div class="col margin gradient-l-r" style="opacity: {1-progress};" >
                    <h1 >Take a selfie</h1>
                    <img class="bottom-fade" src={`${base}/take-selfie.png`} alt="Take a selfie" />
                </div>
            </StickyLayer>
            <StickyLayer offset={{top: 1.2, bottom: 2}} let:progress>
                <div class="col margin gradient-l-r" style="opacity: {1-progress};">
                    <h1>Choose a style</h1>
                    <img class="bottom-fade" src={`${base}/select-style.png`} alt="Select a style" />
                </div>
            </StickyLayer>
            <StickyLayer offset={{top: 2.2, bottom: 3}} let:progress>
            <div class="col margin gradient-l-r" style="opacity: {1-progress};">
                <h1>Book a time</h1>
                <img class="bottom-fade" src={`${base}/book-time.png`} alt="Book a time" />
            </div>
            </StickyLayer>
        </Parallax>
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
                        font-size: var(--label-medium);
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
</style>
