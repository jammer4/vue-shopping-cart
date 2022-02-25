<script>
  export default {
    props: ['toggle', 'cart', 'removeFromCart'],
    data() {
      return {
        total: 0.00
      }
    },
    methods: {
      getTotal() {
        this.total = 0.00;
        this.$props.cart.forEach(element => {
          this.total += element.price;
        }); 
      }
    },
    beforeUpdate() {
      this.getTotal();
    }
  };
</script>

<template>
  <div class="bg">
    <div class="cart">
      <a @click="toggle">X</a>
      <div class="items">
        <h3 v-if="cart.length < 1">Cart is Empty</h3>
        <h3 v-else v-for="product in cart">{{ product.productName }} $ {{ product.price.toFixed(2) }} <a @click="removeFromCart(product.id)">Remove</a></h3>
        <h1>Total: ${{ this.total.toFixed(2) }}</h1>
      </div>
    </div>
  </div>
</template>

<style>
  .bg {
    width: 100vw;
    height: 100vh;
    background-color: rgba(235, 228, 228, 0.699);
    position: fixed;
    top: 0;
  }

  .cart {
    width: 40%;
    height: 800px;
    background-color: rgb(32, 32, 32);
    color: white;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    margin: auto;
    margin-top: 100px;
    border-radius: 10px;
    box-shadow: 10px 10px 8px #888888; 
  }

  .cart a {
    float: right;
    margin: 20px;
    font-size: 1.5rem;
  }

  .cart a:hover {
    cursor: pointer;
  }

  .items {
    width:80%;
    margin: 20px;
    margin-top: 20px;
    float: left;
  }

  .items a {
    float: none;
    font-size: 1rem;
    color: red;
  }
</style>