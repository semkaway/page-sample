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
            <form class="form__form" @submit="submitForm">
                <label class="form__label" for="form__email">Электронная почта</label>
                <input type="email" name="form__email" v-model="email" placeholder="example@email.com" class="form__input" :class="{'form__input--error': emailError}">
                <p v-if="emailError" class="form__text--error">Введите вашу электронную почту</p>
                <label class="form__checkbox">
                    <p class="checkbox__text">Я соглашаюсь с <span class="form__link">Условиями пользования</span> и принимаю <span class="form__link">Политику конфиденциальности</span></p>
                    <input id="checkbox" class="form__checkbox--hidden" type="checkbox">
                    <span class="form__checkmark" :class="{'form__input--error': checkboxError}"></span>
                </label>
                <p v-if="checkboxError" class="form__text--error">Подтвердите, что вы прочитали условия и согласны с ними</p>
                <TheButton class="form__button" type="submit" text="Связаться с клиникой"/>
            </form>
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
                email: "",
                emailError: false,
                checkboxError: false
            }
        },
        methods: {
            closeForm() {
                this.$parent.formVisible = false
            },
            submitForm(e) {
                e.preventDefault()
                let checkbox = document.getElementById('checkbox')
                this.checkboxError = false
                this.emailError = false
                if (this.email == "") {
                    this.emailError = true
                }
                if (checkbox.checked == false) {
                    this.checkboxError = true
                }
                else if(this.email != "" && checkbox.checked) {
                    checkbox.checked = false
                    this.email = ""
                    console.log("submittng form")
                }
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
        margin-bottom: 8px;
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

    .form__checkmark:after {
        content: "";
        position: absolute;
        display: none;
    }

    .form__checkbox input:checked ~ .form__checkmark:after {
        display: block;
    }

    .form__checkbox .form__checkmark:after {
        left: 5px;
        top: 1px;
        width: 5px;
        height: 8px;
        border: solid rgba(0, 0, 0, 0.7);
        border-width: 0 2px 2px 0;
        -webkit-transform: rotate(45deg);
        -ms-transform: rotate(45deg);
        transform: rotate(45deg);
    }

    .form__button {
        margin-top: 40px;
    }

    .form__text--error {
        margin-top: 4px;
        margin-bottom: 0px;
        font-size: 13px;
        line-height: 15px;
        color: #DD2C00;
    }

    .form__input--error {
        border-color: #DD2C00;
    }

</style>
