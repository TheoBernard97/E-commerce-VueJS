<template>
  <div class="card">
    <img src="http://placehold.it/400x250/000/fff" class="card-img-top" alt="placeholder" />
    <div class="card-body">
      <h5 class="card-title">{{ product.name }}</h5>
      <p class="card-text">{{ product.description }}</p>
      <div class="card-bottom">
        <p class="price">{{ product.price | currency }}</p>
        <p
          class="stock"
          v-bind:class="{ few: product.inStock < 10, none: product.inStock == 0 }"
        >{{ product.inStock }} in stock</p>
        <button type="button" class="btn btn-success btn-sm">Add to cart</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: ["product"],
  filters: {
    currency: function (value) {
      let formatter = Intl.NumberFormat("en-US", {
        style: "currency",
        currency: "USD",
        minimumFractionDigits: 0,
      });

      return formatter.format(value);
    },
  },
};
</script>

<style scoped>
.card {
  text-align: left;
  display: flex;
  flex-direction: column;
}

.card-body {
  display: flex;
  flex-direction: column;
  padding: 1rem;
}

.card-text {
  font-size: 0.9rem;
}

.card-bottom {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.price {
  font-weight: bold;
}

.card-bottom * {
  margin: auto 0;
}

.few {
  color: orange;
}

.none {
  color: red;
}
</style>