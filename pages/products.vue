<template>
  <section>
    <h1>{{ title }}</h1>

    <v-alert> Display the products here </v-alert>
  </section>
</template>

<script>
import ProductService from "@/services/ProductService.js";

export default {
  name: "ProductPage",
  data() {
    return {
      title: "Products",
      products: []
    };
  },
  mounted() { // This will get called when the page begins to load
    this.getProducts(); 
  },
  methods: {
    async getProducts() {
      const products = await ProductService.getProducts();
      this.products = products;
    }
  }
};
</script>

<style>
</style>