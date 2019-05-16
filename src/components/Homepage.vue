<template>
  <main class="homepage">
      <img src="@/assets/img/main-img.png" class="homepage__img">
      <div class="homepage__info">
          <p class="homepage__info__paragraph">Израиль, Тель-Авив</p>
          <p class="homepage__info__headline">Медицинский центр Анадолу</p>
          <div class="homepage__homepage__quote__author">
              <homepage__quote__author image="img/logo1.png" title="JCI" info="Joint Commission International"/>
              <homepage__quote__author image="img/logo1.png" title="JCI" info="Joint Commission International"/>
              <homepage__quote__author image="img/logo2.png" title="ESMO" info="European Society for Medical Oncology"/>
          </div>
          <div class="homepage__quote">
              <img src="@/assets/img/quotes.png" alt="quotes" class="homepage__quote__image">
              <p class="homepage__quote__text">Если тебе тяжело, значит ты поднимаешься в гору.
                  Тебе легко, значит ты летишь в пропасть. Если драгоценный камень попадает в грязь, он остается драгоценностью.
                  Если пыль подымается к небу, она остается пылью.</p>
              <div class="homepage__quote__author">
                  <div class="homepage__quote__author__text-holde">
                      <div>
                          <p class="homepage__quote__author__text-holder__text homepage__quote__author__text-holder__text--bold">Риккардо Розати</p>
                          <p class="homepage__quote__author__text-holder__text homepage__quote__author__text-holder__text--muted">Доктор в Медицинском центре Анадолу</p>
                      </div>
                  </div>
                  <div class="homepage__quote__author__image-holder">
                      <img class="homepage__quote__author__image" src="@/assets/img/author.png">
                  </div>
              </div>
          </div>
      </div>
      <div class="homepage__button-holder" hidden>
          <button type="button" class="homepage__button-holder__button">Связаться с клиникой</button>
      </div>
  </main>
</template>

<script>
import InfoBlock from '@/components/InfoBlock'

export default {
    name: 'Homepage',
    components: {'homepage__quote__author': InfoBlock}
}

</script>

<style >

.homepage__quote__author {
    display: flex;
    flex-direction: row;
}

.homepage__quote__author__text-holder {
    display: flex;
    align-items: center;
}

.homepage__quote__author__text-holder__text--bold {
    margin-top: 12.42px;
    font-weight: bold;
    font-size: 16px;
    line-height: 19px;
    color: rgba(0, 0, 0, 0.87);
}

.homepage__quote__author__text-holder__text--muted {
    font-size: 13px;
    line-height: 17px;
    color: rgba(0, 0, 0, 0.6);
}

.homepage__quote__author__image-holder {
    width: 48px;
    height: 48px;
    margin-left: 25px;
}


.homepage__quote__author__text-holder {
    margin-left: 0;
}

.homepage__quote__author__text-holder__text {
    margin: 0;
    margin-bottom: 2px;
}

.homepage__button-holder__button {
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
}

@media screen and (max-width: 600px) {

    .homepage__img {
        width: 100%;
        height: 204px;
    }

    .homepage__info {
        padding-left: 16px;
        padding-right: 16px;
    }

    .homepage__info__paragraph {
        margin: 0;
        margin-top: 5px;
        font-size: 16px;
        line-height: 19px;
        color: rgba(0, 0, 0, 0.87);
    }

    .homepage__info__headline {
        margin: 0;
        margin-top: 5px;
        font-weight: bold;
        font-size: 32px;
        line-height: 37px;
        color: rgba(0, 0, 0, 0.87);
    }

    .homepage__homepage__quote__author {
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
