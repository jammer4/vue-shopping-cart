<script>
  export default {
    props: ['toggle']
  };
</script>

<template>
  <nav>
    <ul>
      <li><h2>The Guitar Shop</h2></li>
      <li><a @click="toggle"><h2>Cart</h2></a></li>
    </ul>
  </nav>
</template>

<style scoped>
  nav {
    background-color: black;
    color: white;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    height: 70px;
  }

  ul {
    margin: 0;
    padding: 0;
  }
  
  li {
    list-style-type: none;
    float: left;
    margin-left: 20px;
    margin-right: 20px;
  }

  img {
    width: 50px;
    border-radius: 25px;
    margin-top: 10px;
  }

  a:hover {
    cursor: pointer;
  }
</style>