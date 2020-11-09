<script>
    export let value = 0;
</script>

<div class="result">
    {value}
</div>

<style>
    .result {
        position: relative;
        width: 320px;
        height: 80px;
        padding: 8px;
        overflow: hidden;
        background-color: rgba(19, 19, 19, .64);
        font-size: 32px;
        line-height: 2;
        color: #60d63c;
        text-align: right;
        direction: rtl;
        white-space: nowrap;
        box-sizing: border-box;
    }    
</style>