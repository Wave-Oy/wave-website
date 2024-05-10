<script>
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
            <Button handler={handleClick} text={text} shape="rectangle" size="medium" layout="label" color="accent" disabled={isChecked}/>
            <input type="text" bind:value={text}>
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
