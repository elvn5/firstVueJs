<template>
  <div class="header">
    <b-container class="bv-example-row header__content">
      <b-row>
        <b-col class='header__desc'>
            <h2>Express Delivery</h2>
            <p>
                Транспортная компания, оказывает полный комплекс логистических услуг по доставке всех видов грузов автомобильным, железнодорожным и воздушным транспортом из любой точки мира,  включая услуги по складированию, таможенному оформлению, страхованию и полному сопровождению грузов. Мы работаем со всеми видами грузов: опасными, рефрижераторными, комплектными, сборными, негабаритными, тяжеловесными, контейнерными.
            </p>
        </b-col>
        <b-col class="header__form"><Form/></b-col>
      </b-row>
    </b-container>
  </div>
</template>


<script>
import Form from './Form'
export default {
    components:{
        Form
    }
}
</script>

<style scoped>
.header {
  background-image: url("../img/bgimage.jpg");
  background-size: cover;
  height: 100vh;
}
.header__content{
    padding-top: 200px;
}

.header__desc{
    background: #fc0; /* Цвет фона */
    box-shadow: 0 0 10px rgba(0,0,0,0.5); /* Параметры тени */
    padding: 10px;
}
.header__form{
    background-color: #fff;
    margin-left: 20px;
    box-shadow: 0 0 10px rgba(0,0,0,0.5); /* Параметры тени */
}
</style>
