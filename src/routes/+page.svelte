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
        <!-- <header>
            <Button handler={handleClick} text={text} shape="rectangle" size="medium" layout="label" color="accent" disabled={isChecked}/>
            <input type="text" bind:value={text}>
            <input type="checkbox" bind:checked={isChecked} />
        </header> -->

        <section class="main-content">
            <!-- Hook section -->
            <div id="form-section" class="row">
                <div class="col">
                    <h1 class="section-title gradient-l-r">Choosing a hairstyle was hard...</h1>
                    <h1 class="section-title gradient-l-r margin-bottom">Not anymore</h1>
                    <Button handler={handleClick} text="Sign up for a Beta" shape="rectangle" size="xlarge" layout="label" color="accent" disabled={false}/>
                </div>
                <div class="col">
                    <img src={`${base}/design-preview.png`} alt="Design Preview" />
                </div>
            </div>

            <div class="arrow-down">
                <FaChevronDown />
            </div>

            <!-- Three picture section -->
            <h1 class="section-title gradient-r-l">Simplify</h1>
            <div class="row">
                <div class="col margin">
                    <h1 class="gradient-l-r">Take a selfie</h1>
                    <img class="bottom-fade" src={`${base}/take-selfie.png`} alt="Take a selfie" />
                </div>
                <div class="col margin">
                    <h1 class="gradient-l-r">Select a style</h1>
                    <!-- Image -->
                    <img class="bottom-fade" src={`${base}/select-style.png`}  alt="Select a style" />
                </div>
                <div class="col margin">
                    <h1 class="gradient-l-r">Book a time</h1>
                    <!-- Image -->
                    <img class="bottom-fade" src={`${base}/book-time.png`}  alt="Book a time" />
                </div>
        </section>
    </div>
</div>

<style lang="scss">
    .main-content {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;

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
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
    }

    .gradient-r-l {
        background: linear-gradient(to right, var(--blue-700), #4585E5, var(--blue-800));
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
    }

    .bottom-fade {
        -webkit-mask-image: linear-gradient(to bottom, rgba(0,0,0,1), rgba(0,0,0,1), rgba(0,0,0,1), rgba(0,0,0,0));
        -webkit-mask-size: 100% 90%;
        -webkit-mask-repeat: no-repeat;
        -webkit-mask-position: left top, left bottom;
    }

    .arrow-down {
        margin-bottom: 4rem;
        width: 5rem;

        // Doesn't work
        background: linear-gradient(to right, var(--blue-700), #4585E5, var(--blue-800));
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;

        color: var(--blue-700);
    }
</style>
