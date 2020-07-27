<template>
  <div id="app">
    <div class="products">
      <ProductCard v-for="product in products" v-bind:key="product.id" v-bind:product="product" />
    </div>
  </div>
</template>

<script>
import ProductCard from "./components/ProductCard.vue";

export default {
  name: "App",
  components: {
    ProductCard,
  },
  data() {
    return {
      products: [
        {
          id: 1,
          name: "MacBook Pro (15 inch)",
          description:
            "This laptop has a super crisp Retina display. Yes, we know that it's overpriced...",
          price: 2999,
          inStock: 50,
        },
        {
          id: 2,
          name: "Samsung Galaxy Note 7",
          description:
            "Unlike the overpriced MacBook Pro, we're selling this one a bit cheap, as we heard it might explode...",
          price: 299,
          inStock: 755,
        },
        {
          id: 3,
          name: "HP Officejet 5740 e-All-in-One-printer",
          description:
            "This one might not last for so long, but hey, printers never work anyways, right?",
          price: 149,
          inStock: 5,
        },
        {
          id: 4,
          name: "iPhone 7 cover",
          description:
            "Having problems keeping a hold of that phone, huh? Ever considered not dropping it in the first place?",
          price: 49,
          inStock: 42,
        },
        {
          id: 5,
          name: "iPad Pro (9.7 inch)",
          description:
            "We heard it's supposed to be pretty good. At least that's what people say.",
          price: 599,
          inStock: 0,
        },
        {
          id: 6,
          name: "OnePlus 3 cover",
          description:
            "Does your phone spend most of its time on the ground? This cheap piece of plastic is the solution!",
          price: 19,
          inStock: 81,
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
}

.products {
  display: grid;
  margin: 2% 3%;
  justify-content: center;
  grid-template-columns: repeat(auto-fill, 400px);
  grid-gap: 30px 2%;
}
</style>
