<template>
  <b-container>
    <b-row align-v="center mt-3">
      <ProductCard
        v-for="product in products"
        :key="product.id"
        :title="product.title"
        :image="product.image"
      ></ProductCard>
    </b-row>
    <div v-if="!loaded" class="text-center mt-5">
      <b-spinner class="text-center" label="Spinning"></b-spinner>
      <br />
      <small>Aguarde....</small>
    </div>
  </b-container>
</template>

<script>
// @ is an alias to /src
import ProductCard from "@/components/ProductCard.vue";

export default {
  name: "Home",
  data() {
    return {
      products: [],
      loaded: false,
    };
  },
  components: {
    ProductCard,
  },
  mounted() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      //aqui estou chamando a api do mockoon
      const res = await fetch("http://localhost:7189/v1/products/");
      const val = await res.json();
      this.products = val;
      this.loaded = true;
    },
  },
};
</script>
