<template>
  <div>
    <Navbar />

    <b-container class="orders__list">
      <b-row>
        <b-col>
          <ul>
            <li v-for="item of orders" :key="item.id">
         <div>
           ID: {{item.id}} 
           </div>    
           <div>
             {{ item.name}} 
              {{item.surname}}
           </div>
              <div>
               Номер: {{item.number}}
              </div>
              
            </li>
          </ul>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Navbar from "../components/Navbar";
import axios from "axios";
export default {
  data() {
    return{
      orders: []
    }
    
  },
  async created() {
    try {
      const res = await axios.get(`http://localhost:3000/orders`);
      this.orders = res.data;
      console.log(this.orders);
    } catch (e) {
      console.error(e);
    }
  },
  name: "App",
  components: {
    Navbar,
  },
};
</script>

<style scoped>
.orders__list {
  margin-top: 100px;
}
ul{
  list-style-type: none;
  padding: 0;
  margin: 0;
}
li{
  display: flex;
  justify-content: space-around;
  border: 1px solid #ccc;
}
</style>
