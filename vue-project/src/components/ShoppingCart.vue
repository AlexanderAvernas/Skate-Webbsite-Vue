<template>
  <h1>SKATEBOARDS</h1>
  <p>Total: {{ totalPrice }}SEK</p>

  <div class="col">
    <div class="card">
      <div class="products-shop" v-for="product in products" :key="product.id">
        <div class="card-body">
          <img :src="product.img" class="card-img-top" alt="Product Image" />
          <h5 class="card-title">{{ product.name }}</h5>
          <h6 class="card-text">{{ product.price }}</h6>
        </div>
        <div>
          <button class="primary-button" @click="addToCart(product.id)">
            Add To Cart
          </button>
        </div>
      </div>
      <div></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [],
      totalPrice: 0,
    };
  },
  created() {
    fetch("skate.json")
      .then((response) => response.json())
      .then((products) => {
        this.products = products;
      });
  },
  methods: {
    addToCart(id) {
      const product = this.products.find((product) => product.id === id);
      const price = parseFloat(product.price.replace(/kr|SEK/, ""));
      this.totalPrice += price;
    },
  },
};
</script>

<style scoped>
h1 {
  text-align: center;
  margin-top: 2rem;
  margin-bottom: 5rem;
}

.col {
  display: flex;
  justify-content: space-evenly;
}
.card {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-evenly;
}
.products-shop {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  border: 1px solid black;
  border-radius: 1rem;
  margin: 5rem;
  width: 18rem;
}
.primary-button {
  margin-bottom: 1rem;
}
</style>
