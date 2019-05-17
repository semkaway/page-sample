<template>
  <main>
      <contact-form v-if="formVisible" id="contactForm"/>
      <div v-else class="homepage">
          <carousel class="homepage__carousel" hidden/>
          <div class="homepage__images">
              <img src="@/assets/img/main-img.png">
          </div>
          <div class="homepage__info">
              <p class="info__paragraph">Израиль, Тель-Авив</p>
              <p class="info__headline">Медицинский центр Анадолу</p>
              <div class="info-block-holder">
                  <info-block image="img/logo1.png" title="JCI" info="Joint Commission International"/>
                  <info-block image="img/logo1.png" title="JCI" info="Joint Commission International"/>
                  <info-block image="img/logo2.png" title="ESMO" info="European Society for Medical Oncology"/>
              </div>
              <div class="homepage__quote">
                  <img src="@/assets/img/quotes.png" alt="quotes" class="homepage__quote__image">
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
import TheCarousel from '@/components/TheCarousel'
import TheButton from '@/components/TheButton'

export default {
    name: 'Homepage',
    components: {
                    'contact-form': TheForm,
                    'info-block': InfoBlock,
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

/* .homepage__button-holder__button {
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
} */

@media screen and (max-width: 600px) {

    .homepage__carousel {
        display: block;
    }

    .homepage__images {
        visibility: hidden;
        display: none;
    }

    .homepage__info {
        padding: 16px;
        box-sizing: border-box;
    }

    .info__paragraph {
        margin: 0;
        font-size: 16px;
        line-height: 19px;
        color: rgba(0, 0, 0, 0.87);
    }

    .info__headline {
        margin: 0;
        margin-top: 5px;
        font-weight: bold;
        font-size: 32px;
        line-height: 37px;
        color: rgba(0, 0, 0, 0.87);
    }

    .info-block-holder {
        margin-top: 24px;
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
