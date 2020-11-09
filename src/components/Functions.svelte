<script>
    import Button from './Button.svelte'
    import { createEventDispatcher } from 'svelte'

    let dispatcher = createEventDispatcher();

    function onContentClear({detail}) {
        dispatcher("contentclear", detail)
    }

    function onDelete({detail}) {
        dispatcher("delete", detail)
    }

</script>

<section class="functions">
    <Button type="button-long-text" text="clear" on:click={onContentClear} />
    <Button text="&larr;" on:click={onDelete} />
</section>

<style>
    .functions {
        float: left;
        width: 240px;
    }
</style>