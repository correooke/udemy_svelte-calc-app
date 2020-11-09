<script>
    import { createEventDispatcher } from 'svelte'

	export let type = "";
	export let text;
    let dispatcher = createEventDispatcher();
    
    function onClick() {
        dispatcher("click", text)
    }

</script>

<button class={type} on:click={onClick}>
	<span>{text}</span>
</button>

<style>

    button {
        outline: none;
        border: 0;
        padding: 16px;
        font-size: 20px;
        line-height: 1;
        background-color: transparent;
        color: #ffce5c;
        transition: all 300ms;
        border: 1px solid #0001;
    }

    button:hover {
        color: #00a3f5;
        border: 1px solid #ffce5c22;
    }

    .button-long-text {
        font-size: 14px;
    }
</style>