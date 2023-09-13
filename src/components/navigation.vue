<template>
    <div class="header">
      <h1>Spa project</h1>
      <div class="nav">
        <router-link to="catalog"><p>Каталог</p></router-link>
        <router-link to="cart"><p>Корзина({{ this.$store.state.cartCount }})</p></router-link>
        <router-link to="orders"><p>Заказы</p></router-link>
        <router-link v-if="!this.$store.getters.isAuthenticated" to="login"><p>Вход</p></router-link>
        <router-link v-if="!this.$store.getters.isAuthenticated" to="register"><p>Регистрация</p></router-link>
        <router-link v-if="this.$store.getters.isAuthenticated" to="logout" @click="logout"><p>Выход</p></router-link>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "header",
    methods: {
      logout() {
        this.$store.dispatch('logout')
      },
    }
  }
  </script>
  
  <style scoped>
  .header {
    display: inline-block;
    margin-left: 10px;
    justify-content: space-around;
    align-items: center;
    margin-top: 10px;
    margin-bottom: 30px;
  }
  .header > h1 {
   text-align: center;
    
    
  }
  
  .nav {
    margin-top: 40px;
    font-size: 23px;
    margin-bottom: 30px;
    width: 1000px;;
    display: block;
    justify-content: center;
  }
  
  a {
    font-weight: bold;
    color: #213c4f;
    text-decoration: none;
  }
  
  a.router-link-exact-active {
    color: rgb(57, 36, 248);
  }
  </style>
  <style>
  *{
    background-color: lightblue;
    margin: 0;
    padding: 0;
  }
  </style>