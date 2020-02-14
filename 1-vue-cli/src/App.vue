<template>
  <div class="container">
    <!--<myComp></myComp> -->
    <div class="cart">
      <h3> BASKET</h3>
        <ul>
            <li v-for="item in cartItems" :key="item.id"> {{item.title}}</li>
        </ul>
      <p v-if="cartItems.length == 0">Sepetiniz bos, Alisverisinize hemen baslayabulirsiniz...</p>
    </div>
   
    <Product @addToCart="cartItems.push($event)" :productProp="product" v-for="product in productList" :key="product.id"/>
  


  </div>
</template>

<script>
//import MainContainer from "@/components/MainContainer"
import Product from "@/components/Product"
  export default {
    components: {
      //myComp : MainContainer,
      Product
    },
    data() {
      return {
        productList: [
                {
                    id: 1,
                    title : "MacBook Pro",
                    price : "100",
                    count : "0",
                    description: "Description 1"
                },
                {
                    id: 2,
                    title : "iPhone",
                    price : "50",
                    count : "100",
                    description: "Description 2"
                },
                {
                    id: 3,
                    title : "Klavye",
                    price : "10",
                    count : "1000",
                    description: "Description 3"
                   
                },   
                ],

        cartItems : []
      }
    }
  } 

</script>


<style>
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  .product:hover{
    border:2px solid #666;
    transition: all 1s;
  }

  .cart {
    margin-bottom: 50px;
    text-align: center;
  }
</style>