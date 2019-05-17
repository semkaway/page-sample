<template>
    <button type="button" class="button">{{text}}</button>
</template>

<script>
    export default {
        name: "TheButton",
        props: ['text']
    }
</script>

<style lang="css" scoped>
    .button {
        height: 56px;
        width: 100%;
        background-color: #FB765F;
        border-radius: 32px;
        border: none;
        box-sizing: border-box;
        padding-top: 16px;
        padding-bottom: 16px;
        padding-left: 8px;
        padding-right: 8px;
        color: rgb(255, 255, 255);
        font-weight: 500;
        font-size: 19px;
        line-height: 22px;
        text-align: center;
        outline-color: rgb(255, 255, 255);
    }
</style>
