<script>
    import Button from "$lib/components/Button.svelte";
    let isChecked = false;

    const handleClick = () => {
        console.log("Button clicked");
        console.log("isChecked", isChecked);
    }
</script>

<div class="home">
    <div class="container">
        <header>
            <button class="button-medium button-accent">Hello</button>
            <Button handler={handleClick} text="Button" color="accent" size="medium" disabled={isChecked}/>
            <input type="checkbox" bind:checked={isChecked} />
        </header>
        <section>
            <h1>ASdASASD</h1>
        </section>
    </div>
</div>

<style lang="scss">
    header {

    }
</style>