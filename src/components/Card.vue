<script>
  export default {
    props: ['product', 'addToCart']
  };
</script>

<template>
  <div class="card">
    <h2>{{ product.productName }}</h2>
    <div class="pic">
      <img :src="product.image" />
    </div>
    <h3>$ {{ product.price.toFixed(2) }}</h3>
    <button type="button" @click="addToCart(product)">Add To Cart</button>
  </div>
</template>

<style>
  .card { 
    width: 350px;
    height: 420px;
    background-color: white;
    margin: 25px;
    text-align: center;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    box-shadow: 10px 10px 8px #888888;
    float: left;
  }

  .pic {
    width: 100%;
    height: 250px;
  }
  
  .card img {
    width: 150px;
    margin: auto;
  }
  
  .card button {
    border-radius: 3px;
    background-color: black;
    color: antiquewhite;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
  }
</style>