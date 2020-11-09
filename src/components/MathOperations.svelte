<script>
    import { createEventDispatcher } from 'svelte'
    import Button from './Button.svelte'

    let dispatcher = createEventDispatcher();

    function clickOperation({detail}) {
        dispatcher("clickOperation", detail)
    }

    function clickEqual({detail}) {
        dispatcher("clickEqual")
        console.log("detail", detail)
    }
</script>

<section class="math-operations">
    <Button text="+" on:click={clickOperation} />
    <Button text="-" on:click={clickOperation} />
    <Button text="*" on:click={clickOperation} />
    <Button text="/" on:click={clickOperation} />
    <Button text="=" on:click={clickEqual} />
</section>