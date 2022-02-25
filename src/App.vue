<script>
  import Card from './components/Card.vue';
  import Navbar from './components/Navbar.vue';
  import Cart from './components/Cart.vue';
  import { products } from './products';

  export default {
    data() {
      return {
        showCart: false,
        products: products,
        cart: []
      };
    },
    methods: {
      toggleCart() {
        this.showCart = !this.showCart;
      },
      addToCart(product) {
        this.cart.push(product);
        this.toggleCart();
      },
      removeFromCart(id) {
        this.cart = this.cart.filter(product => product.id != id);
      }
    },
    components: {
    Card,
    Navbar,
    Cart
    } 
  };
</script>

<template>
  <Cart v-show="showCart" :toggle="this.toggleCart" :cart="this.cart" :removeFromCart="this.removeFromCart"/>
  
  <div>
    <Navbar :toggle="this.toggleCart"/>
    <Card v-for="product in this.products" :product="product" :addToCart="this.addToCart" />
  </div>
</template>

<style scoped>
  
</style>
