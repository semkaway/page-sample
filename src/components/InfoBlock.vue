<template>
    <div class="info-block">
        <div class="info-block__image-holder">
            <img class="info-block__image" :src="getImgUrl(image)">
        </div>
        <div class="info-block__text-holder">
            <div>
                <p class="info-block__text-holder__text info-block__text-holder__text--bold">{{title}}</p>
                <p class="info-block__text-holder__text info-block__text-holder__text--muted">{{info}}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'InfoBlock',
    props: ['image', 'title', 'info'],
    methods: {
        getImgUrl(pic) {
            return require('../assets/'+pic)
        }
    }
}
</script>

<style lang="css">
    .info-block {
        display: flex;
        flex-direction: row;
    }

    .info-block__text-holder {
        display: flex;
        align-items: center;
    }

    .info-block__text-holder__text--bold {
        margin-top: 12.42px;
        font-weight: bold;
        font-size: 16px;
        line-height: 19px;
        color: rgba(0, 0, 0, 0.87);
    }

    .info-block__text-holder__text--muted {
        font-size: 13px;
        line-height: 17px;
        color: rgba(0, 0, 0, 0.6);
    }

    @media screen and (max-width: 600px) {

        .info-block {
            margin-bottom: 16px;
        }

        .info-block__image-holder {
            height: 48px;
            width: 48px;
            background-color: #F5F5F5;
            border: 1px solid #C4C4C4;
            box-sizing: border-box;
            border-radius: 58px;
            text-align: center;
            vertical-align: middle;
            position: relative;
        }

        .info-block__image {
            max-height: 100%;
            max-width: 100%;
            width: auto;
            height: auto;
            position: absolute;
            top: 0;
            bottom: 0;
            left: 0;
            right: 0;
            margin: auto;
        }

        .info-block__text-holder {
            margin-left: 9px;
        }

        .info-block__text-holder__text {
            margin: 0;
            margin-bottom: 2px;
        }

    }
</style>
