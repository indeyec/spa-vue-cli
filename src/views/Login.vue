<template>
    <form @submit.prevent="login">
      <h2>Вход</h2>
      
      <br>
      <div>
        <label for="username">Email</label>
        <input id="username" v-model="email" type="text" placeholder="i_love_django_@gmail.com">
      </div>
      <div>
        <label for="password">Password</label>
        <input id="password" v-model="password" type="password" placeholder="password">
      </div>
      <input type="submit" value="Sign in">
      <button @click="$router.push('catalog')">Home Page </button>
    </form>
  </template>
  
  <script>
  export default {
    name: "LoginView",// почта обязательно с @
    data() {
      return {
        email: this.email,
        password: this.password,
      }
    },
    methods: {
      login() {
        const userData = {
          email: JSON.parse(JSON.stringify(this.email)),
          password: JSON.parse(JSON.stringify(this.password)),
        };
        this.$store
            .dispatch('login', userData)
      },
    }
  }
  </script>
  
  <style scoped>
  form > div {
    width: 340px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  form > div > input {
    margin: 10px 0;
    width: 240px;
    height: 30px;
    padding-left: 10px;
    border: 2px solid #2c3e50;
    border-radius: 5px;
  }
  
  form > div > input:focus {
    outline: none;
    border: 2px solid rgb(137, 136, 160);
  }
  
  form > input {
    margin-right: 20px;
    width: 80px;
    height: 35px;
    border: 2px solid #2c3e50;
    border-radius: 5px;
    background: rgba(118, 126, 163, 0.8);
    cursor: pointer;
  }
  form > div > button {
    margin: 10px 0;
    width: 250px;
    height: 30px;
    padding-left: 10px;
    border: 2px solid #2c3e50;
    border-radius: 5px;
  }
  
  form > div > button:focus {
    outline: none;
    border: 2px solid rgb(137, 136, 160);
  }
  
  form > button {
    margin: 20px 0;
    width: 200px;
    height: 35px;
    border: 2px solid #2c3e50;
    border-radius: 5px;
    background: rgba(118, 126, 163, 0.8);
    cursor: pointer;
  }
  </style>