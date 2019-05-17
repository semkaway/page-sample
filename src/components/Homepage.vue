<template>
  <main>
      <div class="homepage">
          <contact-form :class="{'homepage__form': !formVisible}"/>
          <carousel class="homepage__carousel" hidden/>
          <div class="homepage__images">
              <div class="main-image-holder">
                  <img class="main-image" src="@/assets/img/main-img.png" alt="doctor wearing a face mask">
              </div>
              <div class="images__other-images">
                  <div class="other-image-holder">
                      <img class="other-image" src="@/assets/img/img1.png" alt="hospital bed">
                  </div>
                  <div class="other-image-holder">
                      <img class="other-image" src="@/assets/img/img2.png" alt="doctor working">
                  </div>
                  <div class="other-image-holder">
                      <img class="other-image" src="@/assets/img/img2.png" alt="doctor working">
                  </div>
                  <div class="other-image-holder">
                      <img class="other-image" src="@/assets/img/img1.png" alt="hospital bed">
                  </div>
              </div>
          </div>
          <div class="homepage__info">
              <p class="info__paragraph">Израиль, Тель-Авив</p>
              <p class="info__headline">Медицинский центр Анадолу</p>
              <div class="info-block-holder">
                  <info-block class="info-block-holder__item" image="img/logo1.png" title="JCI" info="Joint Commission International"/>
                  <info-block class="info-block-holder__item" image="img/logo1.png" title="JCI" info="Joint Commission International"/>
                  <info-block class="info-block-holder__item" image="img/logo2.png" title="ESMO" info="European Society for Medical Oncology"/>
              </div>
              <div class="homepage__numbers">
                  <numbers-block number="2 000" text="сотрудников"/>
                  <numbers-block number="23 500" text="операций в год"/>
                  <numbers-block number="400" text="докторов"/>
                  <numbers-block number="658" text="коек"/>
              </div>
              <div class="homepage__quote">
                  <img src="@/assets/img/icons/quotes.png" alt="quotes" class="homepage__quote__image">
                  <p class="homepage__quote__text">Если тебе тяжело, значит ты поднимаешься в гору.
                      Тебе легко, значит ты летишь в пропасть. Если драгоценный камень попадает в грязь, он остается драгоценностью.
                      Если пыль подымается к небу, она остается пылью.</p>
                  <div class="quote__author">
                      <div class="quote__author__text-holder">
                          <p class="quote__author__text-holder__text quote__author__text-holder__text--bold">Риккардо Розати</p>
                          <p class="quote__author__text-holder__text quote__author__text-holder__text--muted">Доктор в Медицинском центре Анадолу</p>
                      </div>
                      <div class="quote__author__image-holder">
                          <img class="quote__author__image" src="@/assets/img/author.png">
                      </div>
                  </div>
              </div>
          </div>
          <div class="homepage__button-holder" hidden>
              <TheButton @click.native="showForm()" text="Связаться с клиникой"/>
          </div>
      </div>
  </main>
</template>

<script>
import TheForm from '@/components/TheForm'
import InfoBlock from '@/components/InfoBlock'
import NumbersBlock from '@/components/NumbersBlock'
import TheCarousel from '@/components/TheCarousel'
import TheButton from '@/components/TheButton'

export default {
    name: 'Homepage',
    components: {
                    'contact-form': TheForm,
                    'info-block': InfoBlock,
                    'numbers-block': NumbersBlock,
                    'carousel': TheCarousel,
                    TheButton
                },
    data() {
        return {
            formVisible: false
        }
    },
    methods: {
        showForm() {
            this.formVisible = true
        }
    }
}

</script>

<style>

    .homepage__images {
        height: 511px;
        display: flex;
        flex-direction: row;
    }

    .main-image-holder {
        width: 60%;
    }

    .main-image {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .images__other-images {
        width: 40%;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
    }

    .other-image-holder {
        width: 50%;
        height: 50%;
    }

    .other-image {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .homepage__form {
        position: absolute;
        margin-left: 888px;
        margin-right: 168px;
        margin-top: 413px;
        height: auto;
        box-shadow: 0px 8px 40px rgba(0, 0, 0, 0.24);
        border-radius: 8px;
    }

    .homepage__info {
        padding-left: 168px;
        padding-right: 608px;
        padding-bottom: 46px;
        box-sizing: border-box;
    }

    .info__paragraph {
        margin: 0;
        margin-top: 56px;
        font-size: 16px;
        line-height: 19px;
        color: rgba(0, 0, 0, 0.87);
    }

    .info__headline {
        margin: 0;
        margin-top: 8px;
        font-weight: bold;
        font-size: 32px;
        line-height: 37px;
        color: rgba(0, 0, 0, 0.87);
    }

    .info-block-holder {
        margin-top: 32px;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
    }

    .info-block-holder__item {
        width: 50%;
    }

    .homepage__numbers {
        display: flex;
        direction: row;
        margin-bottom: 32px;
    }

    .quote__author {
        display: flex;
        flex-direction: row;
    }

    .quote__author__text-holder {
        display: flex;
        align-items: center;
    }

    .quote__author__text-holder__text--bold {
        margin-top: 12.42px;
        font-weight: bold;
        font-size: 16px;
        line-height: 19px;
        color: rgba(0, 0, 0, 0.87);
    }

    .quote__author__text-holder__text--muted {
        font-size: 13px;
        line-height: 17px;
        color: rgba(0, 0, 0, 0.6);
    }

    .quote__author__image-holder {
        width: 48px;
        height: 48px;
        margin-left: 25px;
    }

    .quote__author__text-holder {
        margin-left: 0;
        display: block;
    }

    .quote__author__text-holder__text {
        margin: 0;
        margin-bottom: 2px;
    }

    @media screen and (min-width: 1500px) {
        .homepage__images {
            height: 600px;
        }

        .homepage__form {
            margin-left: 1500px;
            width: 384px;
            margin-right: 50px;
            margin-top: 350px;
        }

    }

    @media screen and (min-width: 1030px) and (max-width: 1250px) {
        .homepage__form {
            margin-left: 650px;
            width: 384px;
            margin-right: 50px;
            margin-top: 350px;
        }

        .homepage__info {
            padding-left: 70px;
            padding-right: 575px;
        }

        .info-block-holder__item {
            width: 100%;
        }

        .homepage__numbers {
            display: none;
        }
    }

    @media screen and (min-width: 900px) and (max-width: 1030px) {
        .homepage__form {
            margin-left: 520px;
            width: 384px;
            margin-right: 50px;
            margin-top: 350px;
        }

        .homepage__info {
            padding-left: 70px;
            padding-right: 500px;
        }

        .info-block-holder__item {
            width: 100%;
        }

        .homepage__numbers {
            display: none;
        }
    }

    @media screen and (min-width: 768px) and (max-width: 900px) {
        .homepage__images {
            height: 400px;
        }

        .homepage__form {
            margin-left: 440px;
            margin-right: 70px;
            margin-top: 300px;
        }

        .homepage__info {
            padding-left: 70px;
            padding-right: 450px;
        }

        .info-block-holder__item {
            width: 100%;
        }

        .homepage__numbers {
            display: none;
        }
    }

    @media screen and (max-width: 768px) {

        .homepage__form {
            display: none;
        }

        .homepage__carousel {
            display: block;
        }

        .homepage__images {
            visibility: hidden;
            display: none;
        }

        .homepage__info {
            padding: 16px;
        }

        .info__paragraph {
            margin: 0;
        }

        .info__headline {
            margin-top: 5px;
        }

        .info-block-holder {
            margin-top: 24px;
            flex-direction: column;
        }

        .info-block-holder__item {
            width: 100%;
        }

        .homepage__numbers {
            display: none;
        }

        .homepage__quote__author {
            margin-top: 20px;
            margin-bottom: 20px;
        }

        .homepage__quote {
            margin-top: 16px;
        }

        .homepage__quote__text {
            font-size: 16px;
            line-height: 23px;
            color: rgba(0, 0, 0, 0.87);
        }

        .homepage__button-holder {
            display: block;
            position: sticky;
            bottom: 0;
            height: 88px;
            box-shadow: 0px 0px 4px rgba(0, 0, 0, 0.25);
            background-color: rgba(255, 255, 255);
            padding: 16px;
            box-sizing: border-box;
        }
    }

</style>
