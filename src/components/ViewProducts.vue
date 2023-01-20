<template>
  <div>
    <h1>Products Page</h1>
    <ul class="products-listing">
      <li v-for="product in allproducts" :key="product.id">
        {{ product.title }} || {{ product.price | currency }}
        <button @click="deleteProduct(product.id)">Delete</button>
      </li>
    </ul>
  </div>
</template>
<script>
import { mapGetters, mapActions } from "vuex";
export default {
  data() {
    return {};
  },
  name: "AddProducts",
  filters: {
    currency: function (value) {
      return "₹ " + parseFloat(value).toFixed(2);
    },
  },
  methods: {
    ...mapActions(["getProducts", "deleteProduct"]),
  },
  computed: mapGetters(["allproducts"]),
  created() {
    this.getProducts();
    this.$store.state.products.abc = "xyz";
    console.log(this.$store.state.products.abc);
  },
};
</script>
<style scoped>
.products-listing li {
  background: #fff;
  padding: 15px;
  border-radius: 5px;
  margin-bottom: 20px;
  list-style: none;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.products-listing li button {
  background: #fff;
  border: 1px solid #fff;
  border-radius: 5px;
  color: #000;
  font-size: 16px;
  cursor: pointer;
}
</style>
