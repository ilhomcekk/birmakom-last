<template>
    <div>
        <modal class="min-height" :height="600" :adaptive="true" name="Modal-Delivery">
            <div class="flex flex-col justify-between h-full">
                <div class="delivery__box">
                    <div class="flex justify-end delivery__cancel">
                        <!-- <button @click="hide()"><i class="fas fa-times"></i></button> -->
                    </div>
                    <div class="delivery__title">
                        <h5>Способ доставки</h5>
                    </div>
                    <div class="delivery__button">
                        <button @click="activeBtn = 'btn1'" :class="{active: activeBtn === 'btn1' }" class="btn1">Пункт выдачи</button>
                        <button @click="activeBtn = 'btn2'" :class="{active: activeBtn === 'btn2' }" class="btn2">Курьером</button>
                    </div>
                    <div class="delivery__select my-4">
                        <div>
                            <span class="mt-2">Выберите страну</span>
                            <select class="mt-1" name="" id="">
                                <option value="">Россия</option>
                            </select>
                        </div>
                        <div>
                            <span class="mt-2">Выберите город</span>
                            <select class="mt-1" name="" id="">
                                <option value="">Москва</option>
                            </select>
                        </div>
                    </div>
                    <div class="mt-4" v-if="activeBtn === 'btn1'">
                        <label class="flex items-center mb-3 punkt"><input class="mr-4" name="radio" type="radio" />1 Филиал</label>
                        <label class="flex items-center mb-3 punkt"><input class="mr-4" name="radio" type="radio" />2 Филиал</label>
                        <label class="flex items-center mb-3 punkt"><input class="mr-4" name="radio" type="radio" />3 Филиал</label>
                        <label class="flex items-center mb-3 punkt"><input class="mr-4" name="company" type="radio" />© btc - 20 000сум</label>
                        <label class="flex items-center mb-3 punkt"><input class="mr-4" name="company" type="radio" />© btc - 20 000сум</label>
                        <label class="flex items-center mb-3 punkt"><input class="mr-4" name="company" type="radio" />© aue - 40 000сум</label>
                    </div>
                    <div v-if="activeBtn === 'btn2'">
                        <div class="inputs">
                            <div class="input mb-4">
                                <span>Улица</span>
                                <input class="adress__input" type="text" placeholder="Улица" />
                            </div>
                            <div class="input mb-4">
                                <span>Дом</span>
                                <input class="adress__input" type="text" placeholder="Дом" />
                            </div>
                            <div class="input mb-4">
                                <span>Квартира</span>
                                <input class="adress__input" type="number" placeholder="Квартал" />
                            </div>
                        </div>
                    </div>
                    <div class="delivery__address">
                        <p v-if="!info">Нет сохраненных адресов</p>
                        <p v-else>Бунёдкор 14 32кв</p>
                    </div>
                </div>
                <div class="delivery__bottom">
                    <button @click="address()" class="delivery__pick mb-2 w-full">Выбрать на карте</button>
                    <div class="flex justify-between">
                        <button class="save" type="submit">Сохранить</button>
                        <button @click="hide()" class="cancel" type="submit">Отменить</button>
                    </div>
                </div>
            </div>
        </modal>
    </div>
</template>

<script>
export default {
  data: () => ({
    info: null,
    activeBtn: ''
  }),
  methods: {
    hide () {
      this.$modal.hide('Modal-Delivery')
    },
    address () {
      this.$modal.show('Modal-Address')
      this.$modal.hide('Modal-Delivery')
    }
  }

}
</script>

<style scoped>
    .inputs{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }
    .input{
        display: flex;
        flex-direction: column;
        width: 48%;
    }
    .delivery__cancel button {
        font-size: 26px;
    }
    .delivery__cancel i {
        cursor: pointer;
    }
    .delivery__box {
        padding: 20px 30px;
    }
    .delivery__bottom {
        position: relative;
        padding: 20px 30px;
    }
    .save{
        background: #131E3D;
        border-radius: 8px;
        font-size: 18px;
        line-height: 100%;
        color: #FFFFFF;
        padding: 15px 25px;
        width: 48%;
    }
    .cancel{
        background: #EE4927;
        border-radius: 8px;
        font-size: 18px;
        line-height: 100%;
        color: #FFFFFF;
        padding: 15px 25px;
        width: 48%;
    }
    .delivery__title {
        font-weight: bold;
        font-size: 24px;
        line-height: 100%;
        color: #000000;
    }
    .delivery__button {
        display: flex;
        justify-content: space-between;
        flex-direction: row;
        margin-top: 20px;
    }
    .btn1 {
        background: #D9D9D9;
        border-radius: 8px;
        font-weight: 600;
        font-size: 16px;
        line-height: 100%;
        color: #000000;
        width: 48%;
        height: 50px;
    }
    .btn2 {
        background: #D9D9D9;
        border-radius: 8px;
        font-weight: 600;
        font-size: 16px;
        line-height: 100%;
        color: #000000;
        width: 48%;
        height: 50px;
    }
    .active {
        background: #ffffff;
        color: #131E3D;
        border: 1px solid #131E3D;
        box-sizing: border-box;
        border-radius: 8px;
    }
    .punkt{
        display: flex;
        line-height: 1;
    }
    .delivery__select{
        display: flex;
        justify-content: space-between;
    }
    .delivery__select > div{
        width: 48%;
    }
    .delivery__select select{
        background: #D9D9D9;
        border-radius: 8px;
        font-weight: 600;
        font-size: 16px;
        line-height: 100%;
        color: #000000;
        height: 50px;
        width: 100%;
        text-align: center;
        outline: none;
        -webkit-appearance: media-slider;
        -moz-appearance: none;
        background-image: url("data:image/svg+xml;utf8,<svg fill='darkblue' height='32' viewBox='0 0 24 24' width='32' xmlns='http://www.w3.org/2000/svg'><path d='M7 10l5 5 5-5z'/><path d='M0 0h24v24H0z' fill='none'/></svg>");
        background-repeat: no-repeat;
        background-position-x: 98%;
        background-position-y: 50%;
    }
    .delivery__address {
        margin-top: 20px;
        font-weight: 600;
        font-size: 14px;
        line-height: 100%;
        color: #000000;
    }
    .delivery__pick {
        background: #131E3D;
        border-radius: 8px;
        font-size: 18px;
        line-height: 100%;
        color: #FFFFFF;
        padding: 15px 25px;
    }
    input[type=radio]{
        display: flex;
        align-items: center;
        justify-content: center;
    }
    input[type=radio]:before {
        position: absolute;
        width: 20px;
        height: 20px;
        border-radius: 10px;
        border: 1px solid gray;
        background: #fff;
        content: "";
    }
    input[type=radio]:checked:before{
        border: 1px solid #EE4927;
    }
    input[type=radio]:checked:after {
        position: relative;
        display: inline-block;
        visibility: visible;
        border-radius: 6px;
        width: 12px;
        height: 12px;
        background: #EE4927;
        content: "";
    }
    .adress__input{
        border: 1px solid #131E3D;
        color: #131E3D;
        outline: #131E3D;
        font-size: 16px;
        border-radius: 4px;
        padding: 4px 6px;
        margin-top: 6px;
    }
    @media (min-width: 200px) and (max-width: 600px){
        .delivery__box{
            padding: 12px;
        }
        .delivery__button {
            padding-right: 0;
        }
        .delivery__select{
            padding-right: 0;
        }
        .delivery__select > div{
            width: 48%;
        }
        .delivery__select select{
            font-size: 14px;
            height: 45px;
        }
        .delivery__pick {
            font-size: 14px;
        }
        .delivery__bottom {
            padding: 10px;
        }
        .save{
            font-size: 14px;
        }
        .cancel{
            font-size: 14px;
        }
        .delivery__title {
            font-size: 20px;
        }
        .btn1 {
            font-size: 14px;
            height: 35px;
        }
        .btn2 {
            font-size: 14px;
            height: 35px;
        }
        .delivery__cancel {
            font-size: 22px;
        }
    }
</style>
