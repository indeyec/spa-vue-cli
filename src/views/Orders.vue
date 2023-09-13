<template>
    <h1>Заказы</h1>
    <div v-if="this.$store.state.orders.length > 0">
    <div class="card" v-for="card in $store.state.orders">
      <br>
      <div>
        <p>Заказ №{{ card.id }}</p>
        <div>
          <p>{{ card.order_price }} &#8381;</p>
        </div>
      </div>
     
    </div>
    </div>
    <div v-else>
      <p>Заказов нету</p>
      <br>
      
      <router-link to="cart"><p>Cart</p></router-link>
    </div>
  </template>
  
  <script>
  export default {
    name: "OrderView",
    mounted() {
      this.$store.dispatch('get_order')
    }
  }
  </script>
  
  <style scoped>
 
  
  .card > div {
    display: flex;
    justify-content: space-between;
    padding: 0 30px;
    align-items: center;
  }
  
  .card > div > div {
    width: 80px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  </style>