<template>
    <div class="carousel">
        <img :src="require(`@/assets/img/${currentImg}`)" class="carousel__img">
        <ul class="carousel__list">
            <li
                v-for="(_, index) in carousel"
                class="carousel__list__dot"
                :key="index"
                :class="{'carousel__list__dot--selected': currentElementIndex === index}"
            >
                <button
                    class="carousel__list__indicator-btn"
                    @click='showElement(index)'
                />
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "Carousel",
        data() {
            return {
                carousel: ["main-img.png",
                            "img1.png",
                            "img2.png",
                            "img3.png",
                            "img4.png"],
                currentImg: "main-img.png",
                currentElementIndex: 0
            }
        },
        methods: {
            showElement(index) {
                this.currentElementIndex = index
                this.currentImg = this.carousel[index]
            }
        }
    }
</script>

<style>
    .carousel  {
        width: 100%;
        height: 204px;
        position: relative;
        background: linear-gradient(180deg, rgba(0, 0, 0, 0) 74.06%, rgba(0, 0, 0, 0.24) 100%);
    }

    .carousel__img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .carousel__list {
        list-style-type: none;
        padding: 0;
        margin: 0 auto;
        position: absolute;
        top: 188px;
        left: calc((100% - 16px * 5) / 2);
    }

    .carousel__list__dot {
        height: 8px;
        width: 8px;
        margin-right: 8px;
        border-radius: 50%;
        background: rgba(255, 255, 255, 0.7);
        cursor: pointer;
        display: inline-block;
    }

    .carousel__list__dot--selected {
        background: rgba(255, 255, 255, 1);
        cursor: default;
    }

    .carousel__list__indicator-btn {
        height: 8px;
        width: 8px;
        border-radius: 50%;
        background: transparent;
        border: none;
        outline-color: rgba(255, 255, 255, 0);
    }

    /* STYLES FOR TABLET */

    @media only screen and (max-width: 768px) and (min-width: 426px) {
        .carousel {
            height: 400px;
        }

        .carousel__list__dot {
            height: 12px;
            width: 12px;
        }

        .carousel__list {
            top: 370px;
            left: calc((100% - 20px * 5) / 2);
        }
    }
</style>
