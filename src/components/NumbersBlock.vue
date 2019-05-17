<template>
    <div class="numbers-block">
        <p class="numbers-block__number">{{number}}</p>
        <p class="numbers-block__text">{{text}}</p>
    </div>
</template>

<script>
    export default {
        name: "NumbersBlock",
        props:['number', 'text']
    }
</script>

<style>

    .numbers-block {
        margin-right: 8px;
        height: 61px;
        box-sizing: border-box;
        border: 1px solid #C4C4C4;
        border-radius: 8px;
        padding-left: 16px;
        padding-right: 16px;
        padding-top: 12px;
        padding-bottom: 12px;
        text-align: center;
    }

    .numbers-block__number {
        margin: 0;
        font-weight: bold;
        font-size: 16px;
        line-height: 19px;
    }

    .numbers-block__text {
        margin: 0;
        font-size: 13px;
        line-height: 15px;
    }

</style>
