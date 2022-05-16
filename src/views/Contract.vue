<template>
    <div class="back">
        <Navbar :black="gray" />
        <second-navbar />
        <div class="container mx-auto px-4 xl:px-12 md:px-4 pages">
            <router-link tag="a" to="/">Главная страница / </router-link>
            <a href="#">Мои  договора</a>
        </div>
        <div class="container mx-auto px-4 xl:px-12 md:px-4">
            <div class="title">Мои договора</div>
            <div class="table">
                <table>
                    <tr>
                        <th>ИП</th>
                        <th>ID заказа</th>
                        <th>Статус</th>
                        <th>Посмотреть</th>
                    </tr>
                    <tr>
                        <td>Текст</td>
                        <td>17</td>
                        <td class="paid">Оплачен</td>
                        <td class="download"><i class="far fa-file-lines"></i> Скачать</td>
                    </tr>
                    <tr>
                        <td>Текст</td>
                        <td>17</td>
                        <td class="no__closed">Не закрыт</td>
                        <td class="download"><i class="far fa-file-lines"></i> Скачать</td>
                    </tr>
                    <tr>
                        <td>Текст</td>
                        <td>17</td>
                        <td class="no__closed">Не закрыт</td>
                        <td class="download"><i class="far fa-file-lines"></i> Скачать</td>
                    </tr>
                </table>
            </div>
        </div>
        <Footer />
    </div>
</template>

<script>
import Navbar from '../components/layout/Navbar.vue'
import Footer from '../components/layout/Footer.vue'
import SecondNavbar from '../components/layout/SecondNavbar.vue'
import LocationNavbar from '../components/layout/LocationNavbar.vue'

export default {
  name: 'Contract',
  data: () => ({

  }),
  components: {
    Navbar,
    Footer,
    SecondNavbar,
    LocationNavbar,
  }
}
</script>

<style src="vue-slim-tabs/themes/default.css"></style>
<style scoped>
    .title{
        color: #131E3D;
        font-size: 42px;
        margin-top: 2rem;
        margin-bottom: 3rem;
    }
    .pages a{
        color: #023047;
    }
    .pages a:hover{
        color: #023999;
    }
    .table{
        overflow-x: scroll;
        display: flex;
    }
    table{
        border-spacing: 0;
        width: 100%;
        margin-bottom: 5rem;
    }
    table tr:first-child{
        background: #131E3D;
    }
    table tr:first-child th:first-child{
        border-radius: 8px 0 0 0;
    }
    table tr:first-child th:last-child{
        border-radius: 0 8px 0 0;
    }
    table tr:not(:first-child){
        background: #F8F8FA;
        border-bottom: 1px solid #DBDBDB;
    }
    table tr th{
        font-size: 18px;
        text-align: center;
        padding: 1.5rem 1rem;
        color: #fff;
        white-space: nowrap;
    }
    table tr td{
        text-align: center;
        padding: 1.5rem 1rem;
        font-size: 18px;
        white-space: nowrap;
    }
    .paid{
        color: #06AD49;
    }
    .no__closed{
        color: #DBA20F;
    }
    .download{
        color: #131E3D;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .download i{
        margin-right: 12px;
        font-size: 24px;
    }

    @media (max-width: 600px){
        .pages {
            padding: 20px 16px !important;
        }
        .pages a {
            font-size: 12px;
        }
        .title{
            font-size: 22px;
            margin-bottom: 10px;
        }
        table tr th{
            font-size: 16px;
        }
        table tr td{
            font-size: 14px;
        }
        .download i{
            font-size: 18px;
        }
    }
    

</style>
