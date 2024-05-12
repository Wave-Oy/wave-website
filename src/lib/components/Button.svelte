<script lang="ts">
    export let handler: () => void;
    export let shape: string = "rectangle";
    export let size: string = "medium";
    export let layout: string = "label";
    export let color: string = "primary";
    export let text: string = "Label";
    export let disabled: boolean = false;

    const className = `shape-${shape} size-${size} layoyt-${layout} color-${color}`;

    $: disabled = disabled;
    $: text = text;
</script>

<button class={className} on:click={() => handler()} disabled={disabled}>
    {#if layout == "label"}
        {text}
    {:else if layout == "icon"}
        icon
    {/if}
</button>

<style lang="scss">
button {
    border: none;
    border-radius: 10px;
    padding: 0;
    cursor: pointer;

    &:hover {
        filter: brightness(1.1);
    }

    &:active {
        filter: brightness(0.9);
    }

    &:disabled {
        background-color: var(--background-disabled) !important;
        color: var(--foreground-on-disabled) !important;
        cursor: not-allowed;
    }

    &.color-accent {
        background-color: var(--background-accent);
        color: var(--foreground-on-accent);
    }

    &.size-small {
        width: 200px;
        height: 40px;
        font-size: var(--label-small);
        font-weight: 600;
    }

    &.size-medium {
        width: 250px;
        height: 48px;
        font-size: var(--label-medium);
        font-weight: 600;
    }

    &.size-large {
        width: 300px;
        height: 56px;
        font-size: var(--label-large);
        font-weight: 600;
    }

    &.size-xlarge {
        width: 350px;
        height: 64px;
        font-size: var(--label-xlarge);
        font-weight: 600;
    }
}
</style>
