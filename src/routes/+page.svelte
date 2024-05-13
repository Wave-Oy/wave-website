<script>
    // For icons check: https://svelte-icons.vercel.app/
    import { base } from '$app/paths';
    import FaChevronDown from 'svelte-icons/fa/FaChevronDown.svelte'
    import Button from "$lib/components/Button.svelte";
    let isChecked = false;
    let text = "Button";

    const handleClick = () => {
        console.log("Button clicked");
        console.log("isChecked", isChecked);
    }
</script>

<div class="home">
    <div class="container">
        <header>
            <div class="row">
                <div>
                    <h1 class="gradient-l-r">Choosing a hairstyle<br>has never been easier</h1>
                    <Button handler={handleClick} text="Test sign up" shape="rectangle" size="large" layout="label" color="accent" disabled={false}/>
                </div>
                <div>
                    <img src={`${base}/design-preview.png`} alt="Design Preview" />
                </div>
            </div>
        </header>
        <section class="main-content">
            <!-- Three picture section -->
            <h2 class="gradient-r-l">Simply</h2>
            <div class="row">
                <div class="col margin">
                    <p class="gradient-l-r">Take a selfie</p>
                    <img class="bottom-fade" src={`${base}/take-selfie.png`} alt="Take a selfie" />
                </div>
                <div class="col margin">
                    <p class="gradient-l-r">Select a style</p>
                    <img class="bottom-fade" src={`${base}/select-style.png`} alt="Select a style" />
                </div>
                <div class="col margin">
                    <p class="gradient-l-r">Book a time</p>
                    <img class="bottom-fade" src={`${base}/book-time.png`} alt="Book a time" />
                </div>
        </section>
    </div>
</div>

<style lang="scss">
    .main-content {
        padding-top: 50px;
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
        font-size: var(--paragraph-xlarge);
        font-weight: 600;
        margin: 0;
        padding: 0;
    }
    header h1 {
        font-size: var(--header-large);
        font-weight: 700;
        margin: 0 0 50px 0;
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
