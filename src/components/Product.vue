<template>
    <div class="cardProduct">
      <h2>Каталог</h2>
      <div class="cards">
        <div v-for="card in allProducts.data">
          <h3>{{ card.name }}</h3>
          <p>{{ card.description }}</p>
          <div>
            <span><b>{{ card.price }} &#8381;</b></span>
            <button v-if="this.$store.getters.isAuthenticated" @click="toCart(card)">Добавить в корзину</button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "CardProduct",
    props: ['allProducts'],
    methods: {
      toCart(card) {
        this.$store.dispatch('to_cart', card.id)
        this.$store.dispatch('get_cart', card.id)
      }
    },
  }
  </script>
  
  <style scoped>
  .cards {
    display: flex;
    flex-wrap: wrap;
    width: 60%;
    margin: 0 auto;
  }
  .cards > div {
    width: 40%;
    padding: 10px 20px 40px 20px;
    margin: 30px auto;
    border: 5px solid #000307;
    border-radius: 15px;
    position: relative;
  }
  
  .cards > div:hover {
    border: 2px solid rgb(0, 0, 0);
  }
  
  .cards > div > h3 {
    text-align: left;
    text-indent: 10px;
  }
  
  .cards > div > span {
    position: absolute;
    left: 20px;
    bottom: 15px;
  }
  
  .cards > div > div {
    width: 90%;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: absolute;
    bottom: 15px;
  }
  
  .cards > div > p {
    text-align: left;
    text-indent: 10px;
    margin-bottom: 20px;
  }
  
  .cards > div > div > button {
    color: #2c3e50;
    width: 180px;
    height: 32px;
    font-size: 18px;
    border: 3px solid #2c3e50;
    border-radius: 15px;
    background: rgba(193, 199, 228, 0.8);
    cursor: pointer;
  }
  </style>