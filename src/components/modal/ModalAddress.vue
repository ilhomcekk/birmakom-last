<template>
    <div>
        <modal :width="'90%'" :height="600" :adaptive="true" name="Modal-Address">
            <div class="address__box">
                <div class="flex justify-end delivery__cancel">
                    <button @click="hide()"><i class="fas fa-times"></i></button>
                </div>
                <div class="address__title">
                    <h5>Выбрать на карте</h5>
                </div>
                    <iframe class="map" src="https://www.google.com/maps/embed?pb=!1m14!1m12!1m3!1d196984.47137915707!2d78.4303487599661!3d39.51714459994583!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!5e0!3m2!1sru!2s!4v1646840209206!5m2!1sru!2s" width="100%" height="500" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
                <!-- <div class="grid grid-cols-10 gap-4">
                    <div class="col-span-10 xl:col-span-4 md:col-span-4">
                        
                    </div>
                    <div class="col-span-10 xl:col-span-6 md:col-span-6">
                    </div>
                </div> -->
            </div>
        </modal>
    </div>
</template>

<script>
export default {
  data: () => ({
    activeBtn: ''
  }),
  methods: {
    hide () {
      this.$modal.hide('Modal-Address')
    }
  }
}
</script>

<style scoped>
    .address__box {
        padding: 20px 30px;
    }
    .address__button {
        margin-top: 20px;
    }
    .address__title h5 {
        font-weight: bold;
        font-size: 24px;
        line-height: 100%;
        color: #000000;
    }
    .btn1 {
        border: 1px solid #898989;
        box-sizing: border-box;
        border-radius: 8px;
        padding: 8px 15px;
        font-weight: normal;
        font-size: 16px;
        line-height: 100%;
        color: #898989;
        margin-right: 20px;
    }
    .btn2 {
        border: 1px solid #898989;
        box-sizing: border-box;
        border-radius: 8px;
        padding: 8px 15px;
        font-weight: normal;
        font-size: 16px;
        line-height: 100%;
        color: #898989;
        margin-right: 20px;
    }
    .btn3 {
        border: 1px solid #898989;
        box-sizing: border-box;
        border-radius: 8px;
        padding: 8px 15px;
        font-weight: normal;
        font-size: 16px;
        line-height: 100%;
        color: #898989;
    }
    .delivery__cancel button {
        font-size: 26px;
    }
    .active {
        border: 1px solid #131E3D;
        color: #131E3D;
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
    @media (min-width: 200px) and (max-width: 600px){
        .address__button {
            display: flex;
            flex-wrap: wrap;
        }
        .address__button button {
            margin-top: 10px;
        }
        .address__title h5 {
            font-size: 20px;
        }
        .delivery__cancel button {
            font-size: 22px;
        }
    }

    /* @media (min-width: 769px) and (max-width: 1025px){
        .vm--modal{
            left: 23% !important;
        }
    }

    @media (min-width: 600px) and (max-width: 769px){
        .vm--modal{
            left: 12% !important;
        }
    }

    @media (max-width: 600px){
        .vm--modal{
            width: 100% !important;
            left: 0 !important;
        }
    } */

</style>
