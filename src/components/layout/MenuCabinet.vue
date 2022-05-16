<template>
    <modal :top="0" :width="'100%'" :height="'100%'" name="Menu-Cabinet" class="search__box">
        <i class="close__icon fas fa-times" @click="closeMenu()"></i>
        <ul>
            <li @click="closeMenu()"><router-link tag="a" to="/register">Войти</router-link></li>
            <li @click="closeMenu()"><router-link tag="a" to="/cabinet">Мои данные</router-link></li>
            <li>
                <button v-bind:class="{ active: notification }" class="notification">
                    <!-- <svg  viewBox="0 0 24 24" width="30" height="30" preserveAspectRatio="xMidYMid meet" focusable="false">
                        <g><path d="M10,20h4c0,1.1-0.9,2-2,2S10,21.1,10,20z M20,17.35V19H4v-1.65l2-1.88v-5.15c0-2.92,1.56-5.22,4-5.98V3.96 c0-1.42,1.49-2.5,2.99-1.76C13.64,2.52,14,3.23,14,3.96l0,0.39c2.44,0.75,4,3.06,4,5.98v5.15L20,17.35z M19,17.77l-2-1.88v-5.47 c0-2.47-1.19-4.36-3.13-5.1c-1.26-0.53-2.64-0.5-3.84,0.03C8.15,6.11,7,7.99,7,10.42v5.47l-2,1.88V18h14V17.77z" class="style-scope yt-icon">
                        </path></g>
                    </svg> -->
                    <span class="notification__span" @click="notification = !notification">
                    Уведомление
                    </span>
                    <transition name="fade">
                        <div class="notification__dropdown" v-if="notification">
                            <div class="not-title mt-4">
                                Уведомление
                                <i class="close__notification fas fa-times" @click="notification = !notification"></i>
                            </div>
                            <div class="not-tabs py-2">
                                <div @click="activeBtn = 'btn1'" :class="{active: activeBtn === 'btn1' }" class="not__tab mr-2">Все</div>
                                <div @click="activeBtn = 'btn2'" :class="{active: activeBtn === 'btn2' }" class="not__tab mr-2">Непрочитанные</div>
                            </div>
                            <div v-if="activeBtn === 'btn1'">
                                <div class="flex items-center justify-between py-2 mediaU">
                                    <div class="subtitle">Новые</div>
                                    <span class="subtitle">Все</span>
                                </div>
                                <router-link to="/selleradres" class="flex py-2">
                                    <div class="not__img">
                                        <img src="/img/11 122001.f3674da5.png" alt="not found">
                                    </div>
                                    <div class="not__text">
                                        <b>Miryoqubov_mirasror</b>
                                        <span>отправил сообщение: "Mahsulotga gap yo'q"</span>
                                        <div class="time">39мин назад</div>
                                    </div>
                                </router-link>
                                <router-link to="/selleradres" class="flex py-2">
                                    <div class="not__img">
                                        <img src="/img/11 122001.f3674da5.png" alt="not found">
                                    </div>
                                    <div class="not__text">
                                        <b>Miryoqubov_mirasror</b>
                                        <span>отправил сообщение: "Mahsulotga gap yo'q"</span>
                                        <div class="time">39мин назад</div>
                                    </div>
                                </router-link>
                                <router-link to="/selleradres" class="flex py-2">
                                    <div class="not__img">
                                        <img src="/img/11 122001.f3674da5.png" alt="not found">
                                    </div>
                                    <div class="not__text">
                                        <b>Miryoqubov_mirasror</b>
                                        <span>отправил сообщение: "Mahsulotga gap yo'q"</span>
                                        <div class="time">39мин назад</div>
                                    </div>
                                </router-link>
                                <router-link to="/selleradres" class="flex py-2">
                                    <div class="not__img">
                                        <img src="/img/11 122001.f3674da5.png" alt="not found">
                                    </div>
                                    <div class="not__text">
                                        <b>Miryoqubov_mirasror</b>
                                        <span>отправил сообщение: "Mahsulotga gap yo'q"</span>
                                        <div class="time">39мин назад</div>
                                    </div>
                                </router-link>
                            </div>
                            <div v-else-if="activeBtn === 'btn2'">
                                <div class="flex items-center justify-between py-2 mediaU">
                                    <div class="subtitle">Новые</div>
                                    <span class="subtitle">Непрочитанные</span>
                                </div>
                                <router-link to="/selleradres" class="flex py-2">
                                    <div class="not__img">
                                        <img src="/img/11 122001.f3674da5.png" alt="not found">
                                    </div>
                                    <div class="not__text new">
                                        <b>Miryoqubov_mirasror</b>
                                        <span>отправил сообщение: "Mahsulotga gap yo'q"</span>
                                        <div class="time">39мин назад</div>
                                    </div>
                                </router-link>
                                <router-link to="/selleradres" class="flex py-2">
                                    <div class="not__img">
                                        <img src="/img/11 122001.f3674da5.png" alt="not found">
                                    </div>
                                    <div class="not__text new">
                                        <b>Miryoqubov_mirasror</b>
                                        <span>отправил сообщение: "Mahsulotga gap yo'q"</span>
                                        <div class="time">39мин назад</div>
                                    </div>
                                </router-link>
                            </div>
                        </div>
                    </transition>
                </button>
            </li>
            <li @click="closeMenu()"><router-link tag="a" to="/selected">Избранные</router-link></li>
            <li @click="closeMenu()"><router-link tag="a" to="/selected">Мои договоры</router-link></li>
            <li @click="closeMenu()"><router-link tag="a" to="/message">Мои сообщения</router-link></li>
            <li @click="closeMenu()"><router-link tag="a" to="/selleradres">Как стать продавцам</router-link></li>
            <li @click="closeMenu()"><router-link tag="a" to="/delivery">Доставка</router-link></li>
            <li @click="closeMenu()"><router-link tag="a" to="/">+998 (98) 989-98-98</router-link></li>
        </ul>
        
    </modal>
</template>

<script>
export default {
    name: 'Home',
    data: () => ({
        notification: false,
        activeBtn: '',
    }),
    methods: {
        closeMenu () {
            this.$modal.hide("Menu-Cabinet")
        }
    }
}
</script>

<style scoped>
    .close__icon{
        position: absolute;
        top: 15px;
        right: 15px;
        padding: 5px 10px;
        font-size: 24px;
        color: #fff;
        border-radius: 50%;
    }
    .close__icon:hover{
        background: rgba(155,155,155,0.3);
    }
    .close__notification{
        color: #131E3D;
    }
    .notification{
        border-radius: 50%;
        width: 100%;
        transition: 0.2s linear;
    }
    .notification__span{
        display: flex;
    }
    .notification__dropdown{
        position: absolute;
        top: 0;
        right: 0;
        left: 0;
        bottom: 0;
        background: #fff;
        text-align: left;
        z-index: 9999;
        padding: 10px;
        width: 100%;
        overflow-y: scroll;
    }
    .notification__dropdown::-webkit-scrollbar{
        display: none;
    }
    .not-title{
        display: flex;
        align-items: center;
        justify-content: space-between;
        font-size: 18px;
        color: #131E3D;
        font-weight: 600;
    }
    .not-tabs{
        display: flex;
        overflow-x: scroll;
    }
    .not-tabs::-webkit-scrollbar{
        display: none;
    }
    .not__tab{
        font-size: 14px;
        border-radius: 30px;
        background: #fff;
        color: #131E3D;
        border: 1px solid #e2e2e2;
        padding: 2px 8px;
    }
    .not__tab.active{
        background: rgba(0, 0, 255, 0.502);
        border: 1px solid transparent;
        color: #fff;
    }
    .notification__dropdown div.subtitle{
        font-size: 16px;
        color: #131E3D;
        font-weight: 600;
    }
    .notification__dropdown span.subtitle{
        color: #0000ff80;
    }
    .not__text{
        text-align: left;
        line-height: 110%;
        position: relative;
        width: -webkit-fill-available;
    }
    .not__text.new::before{
        content: '';
        position: absolute;
        height: 10px;
        width: 10px;
        right: 0;
        top: 25%;
        border-radius: 50%;
        background: #0000ff80;
    }
    .notification__dropdown b{
        font-size: 14px;
        margin-right: 4px;
        line-height: 1;
        color: #131E3D;
    }
    .notification__dropdown span{
        font-size: 14px;
        line-height: 1;
        color: #131E3D;
    }
    .time{
        color: #131E3D;
        font-weight: bold;
        font-size: 13px;
        margin-top: 4px;
    }
    .not__img{
        min-width: 60px;
        height: 60px;
        margin-right: 12px;
    }
    .not__img img{
        width: 100%;
        height: 100%;
        object-fit: contain;
        border-radius: 50%;
    }
    ul{
        background: #131E3D;
        height: 100%;
        display: flex;
        flex-direction: column;
        padding-top: 4rem;
    }
    ul li{
        color: #fff;
        padding: 12px;
        text-align: left;
    }
    ul li:hover{
        background: #EE4927;
    }
    ul li a{
        display: flex;
    }
</style>
