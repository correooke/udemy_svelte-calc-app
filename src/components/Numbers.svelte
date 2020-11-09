<script>
    import { createEventDispatcher } from 'svelte'
    import Button from './Button.svelte'

    let dispatcher = createEventDispatcher()

    const numbers = [7, 8, 9, 4, 5, 6, 1, 2, 3, 0]

    function onButtonClick({ detail }) {
        dispatcher("clickNumber", detail);
    }
</script>


<section class="numbers">
    {#each numbers as number (number)}
        <Button
            text={number.toString()}
            on:click={onButtonClick} />
    {/each}
</section>

<style>

    .numbers {
        width: 240px;
        float: left;
    }

</style>  