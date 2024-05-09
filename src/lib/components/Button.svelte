<script lang="ts">
    export let handler: () => void;
    export let color: string = "primary";
    export let size: string = "medium";
    export let text: string = "Placeholder";
    export let disabled: boolean = false;

    $: className = `color-${color} size-${size} ${disabled ? "disabled" : ""}`;

    $: disabled = disabled;
</script>

<button class={className} on:click={() => handler()} disabled={disabled}>
    {text}
</button>

<style lang="scss">
button {
    border: none;
    width: 200px;
    height: 28px;
    border-radius: 5px;
    font-size: 1px;
    cursor: pointer;

    &:hover{
        filter: brightness(1.1);
    }

    &:active{
        filter: brightness(0.9);
    }

    &.color-accent{
        background-color: var(--background-accent);
        color: var(--foreground-on-accent);
    }

    &.size-medium{
        font-size: var(--label-medium);
    }

    &.disabled{
        background-color: var(--background-disabled);
        color: var(--foreground-on-disabled);
        cursor: not-allowed;
    }

}
</style>