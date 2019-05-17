<template>
    <div class="form">
        <button type="button" class="form__close" @click="closeForm()">
            <img src="@/assets/img/close.svg" alt="close form">
        </button>
        <div class="form__info">
            <p class="info__title">Бесшовная пересадка волос методом FUE</p>
            <div class="info__hr"></div>
            <p class="info__text">Медицинская процедура</p>
            <div class="info__hr"></div>
            <p class="info__text">Послеоперационный осмотр</p>
            <div class="info__hr"></div>
            <p class="info__text">Проживание + Транспорт</p>
            <div class="info__hr"></div>
            <div class="info__text">
                <p class="info__text--bold">Итого</p>
                <p class="info__price">$3400</p>
            </div>
            <form class="form__form">
                <label class="form__label" for="form__email">Электронная почта</label>
                <input type="text" name="form__email" :v-model="email" placeholder="example@email.com" class="form__input">
                <label class="form__checkbox">
                    <p class="checkbox__text">Я соглашаюсь с <span class="form__link">Условиями пользования</span> и принимаю <span class="form__link">Политику конфиденциальности</span></p>
                    <input class="form__checkbox--hidden" type="checkbox">
                    <span class="form__checkmark"></span>
                </label>
            </form>
            <TheButton class="form__button" @click.native="showForm()" text="Связаться с клиникой"/>
        </div>
    </div>
</template>

<script>

    import TheButton from '@/components/TheButton'

    export default {
        name: "TheForm",
        components: {TheButton},
        data() {
            return {
                email: String
            }
        },
        methods: {
            closeForm() {
                this.$parent.formVisible = false
            }
        }
    }
</script>

<style>

    .form {
        position: absolute;
        height: 100%;
        width: 100%;
        background-color: rgb(255, 255, 255);
        display: inline-block;
    }

    .form__close {
        position: absolute;
        left: 19px;
        top: 19px;
        width: 18px;
        height: 18px;
        box-sizing: border-box;
        padding: 0;
        background-color: rgb(255, 255, 255);
        border: none;
        outline-color: rgb(255, 255, 255);
    }

    .form__info {
        padding-left: 20px;
        padding-right: 20px;
        box-sizing: border-box;
        margin-top: 80px;
    }

    .info__title {
        margin: 0;
        font-weight: bold;
        font-size: 19px;
        padding-bottom: 8px;
    }

    .info__text {
        margin: 0;
        margin-top: 12px;
        font-size: 16px;
        line-height: 23px;
        color: rgba(0, 0, 0, 0.87);
        display: flex;
    }

    .info__text--bold {
        margin: 0;
        align-self: flex-start;
        font-weight: bold;
    }

    .info__price {
        margin: 0;
        font-weight: bold;
        font-size: 19px;
        margin-left: auto;
    }

    .info__hr {
        margin-top: 8px;
        height: 0px;
        border-top: 1px solid #C4C4C4;
    }

    .form__form {
        display: flex;
        flex-direction: column;
        position: relative;
        margin-top: 37px;
    }

    .form__label {
        font-size: 16px;
        color: rgba(0, 0, 0, 0.87);
    }

    .form__input {
        margin-top: 4px;
        border: 1px solid #DADCE0;
        box-sizing: border-box;
        padding: 16px;
        border-radius: 2px;
        font-size: 19px;
    }

    .form__checkbox {
        margin-top: 16px;
        position: relative;
    }

    .checkbox__text {
        margin: 0;
        font-size: 13px;
        line-height: 17px;
        color: rgba(0, 0, 0, 0.6);
        margin-left: 37px;
    }

    .form__link {
        text-decoration: underline;
    }

    .form__checkbox--hidden {
        position: absolute;
        opacity: 0;
        cursor: pointer;
        height: 0;
        width: 0;
    }

    .form__checkmark {
        position: absolute;
        top: 0;
        left: 0;
        margin-top: 9px;
        height: 18px;
        width: 18px;
        border: 1px solid rgba(0, 0, 0, 0.38);
        box-sizing: border-box;
        border-radius: 2px;
    }

    .form__button {
        margin-top: 40px;
    }

</style>
