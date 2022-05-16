<template>
    <div class="debit__box">
        <modal class="modal__card" :height="'auto'" :adaptive="true" name="Modal-Card">
            <div class="debit__modal">
                <div class="modal__header">
                    <div class="header__title">
                        <h4>Дебетовая или кредитная карта</h4>
                    </div>
                    <div class="header__close">
                        <button @click="hide()"><i class="fas fa-times"></i></button>
                    </div>
                </div>
                <div class="debit__title">
                    <div class="debit__danniy">
                        <h5>Данные карты</h5>
                    </div>
                    <div>
                    </div>
                </div>
                <div class="debit__info">
                    <div class="flex justify-between media-col">
                        <input v-on:keyup.enter="$refs.nth2.focus()" placeholder="Имя" type="text" class="text-black placeholder-gray-600 w-full px-4 py-2.5 mr-2.5 mt-2 text-base transition duration-500 ease-in-out transform border-transparent rounded-lg bg-gray-200  focus:border-blueGray-500 focus:bg-white dark:focus:bg-gray-800 focus:outline-none focus:shadow-outline focus:ring-1 ring-offset-current ring-offset-1 ring-gray-800">
                        <input ref="nth2" v-on:keyup.enter="$refs.nth3.focus()" placeholder="Фамилия" type="text" class="text-black placeholder-gray-600 w-full px-4 py-2.5 ml-2.5 media-l-0 mt-2 text-base transition duration-500 ease-in-out transform border-transparent rounded-lg bg-gray-200  focus:border-blueGray-500 focus:bg-white dark:focus:bg-gray-800 focus:outline-none focus:shadow-outline focus:ring-1 ring-offset-current ring-offset-1 ring-gray-800">
                    </div>
                    <div class="flex media-col-2 justify-between mt-2">
                        <input ref="nth3" v-on:keyup.enter="$event.target.nextElementSibling.focus()" v-on:keypress="NumbersOnly" placeholder="Данные на карты" maxlength="19" :value="cardNumber | formatCardNumber" @input="updateValue" class="text-black placeholder-gray-600 w-full px-4 py-2.5 mt-2 mr-2.5 text-base transition duration-500 ease-in-out transform border-transparent rounded-lg bg-gray-200  focus:border-blueGray-500 focus:bg-white dark:focus:bg-gray-800 focus:outline-none focus:shadow-outline focus:ring-1 ring-offset-current ring-offset-1 ring-gray-800">
                        <input ref="nth4" v-on:keyup.enter="$event.target.nextElementSibling.focus()" v-on:keypress="NumbersOnly" maxlength="2" placeholder="ММ" type="text" class="text-black w-32 mr-2 ml-2.5 placeholder-gray-600 px-4 py-2.5 mt-2 text-base transition duration-500 ease-in-out transform border-transparent rounded-lg bg-gray-200  focus:border-blueGray-500 focus:bg-white dark:focus:bg-gray-800 focus:outline-none focus:shadow-outline focus:ring-1 ring-offset-current ring-offset-1 ring-gray-800">
                        <input v-on:keyup.enter="$refs.lastInput.focus()" v-on:keypress="NumbersOnly" maxlength="2" placeholder="ГГ" type="text" class="text-black w-32 placeholder-gray-600 px-4 py-2.5 mt-2 ml-1.5 text-base transition duration-500 ease-in-out transform border-transparent rounded-lg bg-gray-200  focus:border-blueGray-500 focus:bg-white dark:focus:bg-gray-800 focus:outline-none focus:shadow-outline focus:ring-1 ring-offset-current ring-offset-1 ring-gray-800">
                    </div>
                    <div class="debit__into w-72 mt-2 pr-4">
                        <input v-on:keypress="NumbersOnly" ref="lastInput" maxlength="3" placeholder="CVV" type="text" class="text-black w-full placeholder-gray-600 mt-2 px-4 py-2.5 mt-2 text-base transition duration-500 ease-in-out transform border-transparent rounded-lg bg-gray-200  focus:border-blueGray-500 focus:bg-white dark:focus:bg-gray-800 focus:outline-none focus:shadow-outline focus:ring-1 ring-offset-current ring-offset-1 ring-gray-800">
                    </div>
                </div>
                <div class="debit__bottom">
                    <p><i class="fas fa-lock mr-2"></i><span>Информация о ваших способах оплаты хранится в защищенном режиме.</span></p>
                    <a href="">Условия использования</a>
                </div>
                <div class="debit__footer">
                    <a>Сохранить</a>
                </div>
            </div>
        </modal>
    </div>
</template>

<script>
import VueTheMask from 'vue-the-mask'

export default {
  data: () => ({
    activeBtn: '',
    cardNumber: '',
  }),
  components: {
    VueTheMask,
  },
  methods: {
    hide () {
      this.$modal.hide('Modal-Card')
    },
    updateValue (e) {
      this.cardNumber = e.target.value.replace(/ /g,'');
    },
    NumbersOnly(evt) {
      evt = (evt) ? evt : window.event;
      var charCode = (evt.which) ? evt.which : evt.keyCode;
      if ((charCode > 31 && (charCode < 48 || charCode > 57)) && charCode !== 46) {
        evt.preventDefault();;
      } else {
        return true;
      }
    },
  },
  filters: {
    formatCardNumber (value) {
      return value ? value.match(/.{1,4}/g).join(' ') : '';
    }
  }
}
</script>

<style scoped>
    .debit__box {
        width: 50%;
    }
    .modal__card {
        width: 80%;
    }
    .header__close button {
        font-size: 20px;
    }
    .modal__header {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
    .debit__info {
        display: flex;
        flex-direction: column;
    }
    .debit__bottom p {
        display: flex;
        flex-direction: row;
        font-size: 12px;
        align-items: center;
        justify-content: center;
        color: #999999;
    }
    .debit__bottom a {
        display: flex;
        flex-direction: row;
        justify-content: center;
        font-size: 12px;
        color: #131E3D;
    }
    .debit__bottom {
        margin-top: 25px;
    }
    .header__title h4 {
        font-size: 20px;
        color: #0a0a0a;
        text-align: center;
        font-weight: 500;
    }
    .header__title {
        align-content: center;
        align-items: center;
        text-align: center;
    }
    .debit__modal {
        padding: 20px 20px;
    }
    .debit__danniy {
        color: #999999;
        margin-top: 20px;
    }
    .debit__footer {
        display: flex;
        flex-direction: row;
        justify-content: flex-end;
    }
    .debit__footer a {
        background: #131E3D;
        border-radius: 8px;
        color: #ffffff;
        font-size: 16px;
        padding: 8px 12px;
        margin-top: 20px;
        cursor: pointer;
    }
    .debit__footer a:hover{
        background: #11113D;
    }
    @media (min-width: 320px) and (max-width: 600px) {
        .header__title h4 {
            font-size: 18px;
        }
        input{
            font-size: 14px;
        }
        .media-col{
            flex-direction: column;
        }
        .media-l-0{
            margin-left: 0;
        }
        .media-col-2{
            flex-wrap: wrap;
            margin-top: 0;
        }
        .media-col-2 .w-full{
            margin-right: 0;
        }
        .media-col-2 .w-32{
            width: 48%;
            margin-left: 0;
            margin-right: 0;
        }
        .debit__into{
            width: 100%;
            padding-right: 0;
            margin-top: 0;
        }
    }
</style>
