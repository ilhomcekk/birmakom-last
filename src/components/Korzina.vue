<template>
    <div class="basket__item">
        <div class="far fa-trash-alt korzina-trash"></div>
        <div class="basket__left">
            <input id="check__input" type="checkbox" />
            <div class="basket__image">
                <img src="../assets/image/outdoors-3176153_1920 1 (1).png" alt="">
            </div>
            <div class="basket__box">
                <div class="grid-item">
                    <h4 class="mb-4">POLO  рубашка</h4>
                    <h5 class="mb-4"><span>Белый, XXL - 44</span></h5>
                    <div class="basket__price">
                        <h3>500 ₽</h3>
                    </div>
                </div>
                <div class="grid-item">
                    <div class="bank">В Узбекистан через EMU</div>
                </div>
                <div class="grid-item self-end">
                    <div class="basket__count">
                        <Counter />
                        <h5>Осталось 2 шт</h5>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Counter from '../components/Counter.vue'

export default {
  components: {
    Counter,
  },
}
</script>

<style scoped>
    .korzina-trash{
        font-size: 24px;
        color: #EE4927;
        position: absolute;
        top: 15px;
        right: 15px;
        cursor: pointer;
    }
    .basket__left {
        display: flex;
        flex-direction: row;
        width: 100%;
    }
    .basket__image {
        min-width: 150px;
        width: 150px;
        height: 150px;
        display: flex;
        align-items: center;
        margin-right: 26px;
    }
    .basket__image img{
        margin-top: auto;
        margin-bottom: auto;
    }
    #check__input{
        margin-top: auto;
        margin-bottom: auto;
        margin-right: 10px;
        min-width: 18px;
        height: 18px;
        position: relative;
    }
    #check__input:checked::after{
        content: "\2713";
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 2px;
        position: absolute;
        color: #fff;
        left: 0;
        top: 0;
        height: 100%;
        width: 100%;
        background: #131E3D;
    }
    .basket__item {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        background: #FFFFFF;
        box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.25);
        border-radius: 8px;
        padding: 15px;
        margin-bottom: 1rem;
        position: relative;
    }
    .basket__box {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        column-gap: 10px;
        width: 100%;
    }
    .basket__box h4 {
        font-size: 18px;
        line-height: 1;
        font-weight: bold;
        text-transform: uppercase;
        color: #000000;
    }
    .basket__box h5 {
        font-weight: normal;
        font-size: 16px;
        line-height: 1;
        color: #023047;
    }
    .basket__box h5 span{
        line-height: 1;
    }
    .basket__gray {
        font-weight: normal;
        font-size: 16px;
        line-height: 1;
        color: #898989;
    }
    .basket__count{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    .basket__count h5 {
        margin-top: 15px;
        font-size: 14px;
        line-height: 100%;
        color: #404040;
    }
    .basket__price h3 {
        font-size: 22px;
        line-height: 100%;
        color: #404040;
    }
    .basket__price h4 {
        font-weight: 500;
        font-size: 18px;
        line-height: 22px;
        text-decoration: line-through;
    }
    .basket__price p {
        font-weight: 500;
        font-size: 14px;
        line-height: 17px;
        color: #898989;
    }
    .bank{
        background: #f6f6f6;
        text-align: center;
        padding: 3px;
        line-height: 1;
    }

    @media (max-width: 1000px){
        .basket__price{
            align-items: unset;
        }
        .basket__image{
            margin: auto 16px auto 0;
        }
        .basket__count h5{
            margin-top: 6px;
        }
        .bank{
            padding: 2px;
            font-size: 14px;
        }
    }

    @media (min-width: 600px) and (max-width: 769px){
        .basket__item{
            flex-direction: column;
        }
        .basket__count{
            margin: 1rem 0;
            align-items: flex-start;
            justify-content: unset;
        }
        .basket__gray {
            font-size: 14px;
        }
    }

   @media (min-width: 415px) and (max-width: 600px){
       .korzina-trash{
           top: 15px;
           right: 15px;
           font-size: 22px;
       }
       .basket__price{
           align-items: unset;
       }
       .basket__left{
           width: 100%;
       }
       .basket__box{
           width: 100%;
       }
       .basket__box .mb-4{
           margin-bottom: 10px;
       }
       .basket__box .flex{
           justify-content: space-between;
       }
       .basket__image{
           min-width: 130px;
           width: 130px;
       }
       .basket__image img{
           border-radius: 8px;
       }
       .basket__box h4{
           font-size: 16px;
       }
       .basket__count h5{
           margin-top: 5px;
       }
        .basket__box{
            grid-template-columns: 1fr 1fr;
        }
       .grid-item:first-child{
           grid-column: 1 / 3;
           width: 90%;
       }
       .bank{
           font-size: 10px;
       }
       .grid-item:nth-child(2){
           align-self: flex-end;
       }
       .grid-item:last-child{
           align-self: flex-start;
       }
   }

    @media (max-width: 415px){
        .korzina-trash{
            top: 10px;
            right: 10px;
            font-size: 18px;
        }
        #check__input{
            margin-right: 5px;
        }
        .basket__left{
            width: 100%;
        }
        .basket__item{
            padding: 10px;
        }
        .basket__box{
            width: 100%;
            margin-left: 0;
        }
        .basket__box .flex{
            width: 100%;
            margin-top: 5px;
            justify-content: space-between;
        }
        .basket__box h5{
            margin-top: 5px;
            margin-bottom: 0;
            font-size: 11px;
        }
        .basket__box h5 span{
            font-size: 11px;
        }
        .basket__box h4{
            margin-top: 0px;
            margin-bottom: 0;
            font-size: 12px;
        }
        .basket__image{
            min-width: 80px;
            width: 80px;
            height: auto;
            margin: auto 10px auto 0;
        }
        .basket__image img{
            border-radius: 8px;
        }
        .basket__price h3{
            font-size: 13px;
        }
        .basket__price h4{
            font-size: 14px;
        }
        .basket__gray {
            font-size: 14px;
            line-height: 1;
        }
        .basket__box{
            grid-template-columns: 1fr 1fr;
        }
        .grid-item:first-child{
           grid-column: 1 / 3;
           width: 90%;
        }
        .grid-item:nth-child(2){
           align-self: flex-end;
       }
        .bank{
           font-size: 8px;
        }
        .grid-item:last-child{
            align-self: flex-start;
        }
    }

</style>
