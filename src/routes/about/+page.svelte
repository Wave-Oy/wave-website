<script lang="ts">
    // For icons check: https://svelte-icons.vercel.app/
    import { base } from '$app/paths';
</script>

<div class="about page">
    <div class="container">
        <header class="row">
            <div class="col box-around">
                <h1 class="gradient-l-r">Our job is to make hairstyle easier for everyone.</h1>
                <p>No more endless scrolling through thousands of pictures of supermodels for you, and no more vague pictures for your barber!</p>
            </div>
            <div class="col" style="margin-top: 150px;">
                <img src={`${base}/about-decorations.png`} alt="decorations" class="decorations">
            </div>
        </header>
        <section>
            <div class="row box-around content" style="max-width:800px;">
                <div class="col">
                    <h2 class="gradient-l-r">Our story</h2>
                    <p>
                        “Do you know which hairstyle to get? I just go to Google to scroll through thousands of pictures of hairstyles only to get frustrated and anxious!” 
                        <br>
                        <br>
                        I recall these were the exact words I said to Simo when I first had the idea of wave. We both realised on that call that before every haircut ever, we have had difficulties in selecting a good looking haircut. Essentially wave was born from a mutual need to make choosing hairstyles easier! 
                        <br>
                        <br>
                        Fast forward to today, we are a passionate team of 5 individuals, sharing the same common vision, which has been guiding us since the beginning. Our journey from a simple conversation to winning IdeaRace, South Karelias biggest pitching competition's student category, is a remarkable one, but just the beginning!
                        <br>
                        <br>
                        Now, we're ready for the next stage of our journey. With a clear vision and a passionate team, we are revolutionizing the hairstyling-industry one bold idea at a time! 
                        <br>
                        <br>
                        - Ville Sekki, CEO & Co-Founder
                    </p>
                </div>
                <div class="col headshot-container">
                    <img src={`${base}/headshot_ville.jpg`} alt="Ville Sekki" class="headshot">
                    <p class="headshot-title">Ville Sekki</p>
                </div>

            </div>
            <div class="row">
                <div class="col">
                    <img src={`${base}/about-decorations.png`} alt="decorations" class="decorations">
                </div>
                <div class="col box-around content">
                    <h2 class="gradient-l-r">Why do we do this?</h2>
                    <p>
                        Our job is to make choosing a hairstyle easier for everyone. That's our thing. But our deeper mission is to empower individuals, like you, to discover their ideal self-expression and image.
                        <br>
                        <br>
                        With Wave, we aim to boost everyone's confidence in their appearance. Hairstyling plays a significant role in our overall look, and with Wave, we help you find the best haircut for you, regardless of your hair type. No one needs to resemble a supermodel to shine bright like a diamond!
                        <br>
                        <br>
                        Through innovative technology and personalization, we're making hairstyling accessible, convenient, and perfectly tailored to everyone!
                    </p>
                </div>
            </div>
        </section>

        <section>
            <div class="col box-around content" style="max-width:800px;">
                <h2 class="gradient-l-r center" style="margin-bottom: 25px;">Our amazing team!</h2>
                <div class="team-desktop">
                    <div class="row">
                        <div class="col center">
                            <div class="team-picture-title">
                                <p class="headshot-title center margin-0" style="margin-bottom: 5px;">CEO</p>
                                <p class="headshot-title center margin-0">Ville Sekki</p>
                            </div>
                            <img src={`${base}/team-ville.png`} alt="Ville Sekki" class="team-image desktop">
                        </div>
                        <div class="col center">
                            <img src={`${base}/team-johannes.png`} alt="Johannes Haapanen" class="team-image desktop">
                            <div class="team-picture-title">
                                <p class="headshot-title center margin-0" style="margin-bottom: 5px;">CIO</p>
                                <p class="headshot-title center margin-0">Johannes Haapanen</p>
                            </div>
                        </div>
                        <div class="col center">
                            <div class="team-picture-title" style="margin-top: 50px;">
                                <p class="headshot-title center margin-0" style="margin-bottom: 5px;">CFO</p>
                                <p class="headshot-title center margin-0">Simo Osola</p>
                            </div>
                            <img src={`${base}/team-simo.png`} alt="Simo Osola" class="team-image desktop">
                        </div>
                        <div class="col center">
                            <img src={`${base}/team-georgy.png`} alt="Georgy Pokazeev" class="team-image desktop">
                            <div class="team-picture-title">
                                <p class="headshot-title center margin-0" style="margin-bottom: 5px;">CTO</p>
                                <p class="headshot-title center margin-0">Georgy Pokazeev</p>
                            </div>
                        </div>
                        <div class="col center">
                            <div class="team-picture-title">
                                <p class="headshot-title center margin-0" style="margin-bottom: 5px;">Developer & Designer</p>
                                <p class="headshot-title center margin-0">Tomi Koskinen</p>
                            </div>
                            <img src={`${base}/team-tomi.png`} alt="Tomi Koskinen" class="team-image desktop">
                        </div>
                    </div>
                </div>
                <div class="team-mobile">
                    <div class="col">
                        <div class="col center">
                            <img src={`${base}/team-ville.png`} alt="Ville Sekki" class="team-image mobile">
                            <div class="team-picture-title">
                                <p class="headshot-title center margin-0" style="margin-bottom: 5px;">CEO</p>
                                <p class="headshot-title center margin-0">Ville Sekki</p>
                            </div>
                        </div>
                        <div class="col center">
                            <img src={`${base}/team-johannes.png`} alt="Johannes Haapanen" class="team-image mobile">
                            <div class="team-picture-title">
                                <p class="headshot-title center margin-0" style="margin-bottom: 5px;">CIO</p>
                                <p class="headshot-title center margin-0">Johannes Haapanen</p>
                            </div>
                        </div>
                        <div class="col center">
                            <img src={`${base}/team-simo.png`} alt="Simo Osola" class="team-image mobile">
                            <div class="team-picture-title">
                                <p class="headshot-title center margin-0" style="margin-bottom: 5px;">CFO</p>
                                <p class="headshot-title center margin-0">Simo Osola</p>
                            </div>
                        </div>
                        <div class="col center">
                            <img src={`${base}/team-georgy.png`} alt="Georgy Pokazeev" class="team-image mobile">
                            <div class="team-picture-title">
                                <p class="headshot-title center margin-0" style="margin-bottom: 5px;">CTO</p>
                                <p class="headshot-title center margin-0">Georgy Pokazeev</p>
                            </div>
                        </div>
                        <div class="col center">
                            <img src={`${base}/team-tomi.png`} alt="Tomi Koskinen" class="team-image mobile">
                            <div class="team-picture-title">
                                <p class="headshot-title center margin-0" style="margin-bottom: 5px;">Developer & Designer</p>
                                <p class="headshot-title center margin-0">Tomi Koskinen</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>
</div>


<style lang="scss">
    .about {
        padding-top: 100px;
        padding-bottom: 100px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
    }

    header {
        max-height: 400px;
        margin-top:50px;
    }

    .content {
        margin-top: 200px;
    }

    .row {
        display: flex;
        flex-direction: row;
    }

    .col {
        display: flex;
        flex-direction: column;

        &.box-around {
            max-width: 500px;
        }

        &.headshot-container {
            align-items: center;
            justify-content: center;
            margin-left: 50px;
        }

        .headshot-title {
            font-size: var(--paragraph-large);
            color: var(--foreground-accent);
            font-weight: 500;
        }
    }

    .box-around {
        justify-content: center;
        align-items: center;
        background-color: var(--blue-100);
        padding: 20px 40px 20px 40px;
        border-radius: 20px;
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

    .decorations {
        width: 100%;
        max-width: 300px;
    }

    .headshot {
        border-radius: 50%;
        border: 2px solid var(--foreground-accent);
        width: 250px;
    }
    .margin-0 {
        margin: 0;
    }

    .center {
        display: flex;
        justify-content: center;
        text-align: center;
    }

    .team-image {
        max-width: 150px;
        margin: auto;
        margin-top: -25px;
        margin-bottom: -25px;

        &.desktop {
            margin-top: -25px;
            margin-bottom: -25px;
        }

        &.mobile {
            margin-top: 0;
            margin-bottom: -20px;
        }
    }

    .team-desktop {
            display: block;
        }

    .team-mobile {
        display: none;
    }

    /* Responsive view */
    @media (max-width: 1000px) {
        header {
            margin-top: 25px;
        }
        .decorations {
            display: none;
        }
        .content {
            margin-top: 100px;
        }
        .col.box-around {
            max-width: none;
        }
        .headshot-container {
            display: none;
            /* Make appear below or above the text, idc */
        }
        .team-desktop {
            display: none;
        }

        .team-mobile {
            display: block;
        }
    }
    @media (max-width: 600px) {

        .team-desktop {
            display: none;
        }

        .team-mobile {
            display: block;
        }
        h1 {
            font-size: 8vw;
        }
        h2 {
            font-size: var(--header-small);
        }
    }
</style>
