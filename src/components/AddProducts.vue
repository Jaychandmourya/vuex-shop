<template>
  <div>
    <h1>Add Products</h1>
    <div class="add-product">
      <form @submit.prevent="onSubmit">
        <input
          type="text"
          v-model="title"
          placeholder="Enter Product name..."
        />
        <input
          type="number"
          v-model="price"
          placeholder="Enter Product price..."
        />
        <input type="submit" value="Submit" />
      </form>
    </div>
  </div>
</template>
<script>
import { mapActions } from "vuex";
export default {
  name: "ViewProducts",
  data() {
    return {
      title: "",
      price: "",
    };
  },
  methods: {
    ...mapActions(["addProduct"]),
    onSubmit() {
      this.addProduct({
        title: this.title,
        price: this.price,
        pstatus: true,
      });
    },
  },
};
</script>
<style scoped>
.add-product {
  background: #fff;
  padding: 15px;
  border-radius: 5px;
  margin-bottom: 20px;
}
form {
  display: flex;
  justify-content: space-between;
}
input[type="text"] {
  width: 270px;
  padding: 10px;
  border: 1px solid #2c3e50;
  outline: 0;
}
input[type="submit"] {
  width: 120px;
  background: #2c3e50;
  color: #fff;
  border: 1px #2c3e50 solid;
  cursor: pointer;
}
</style>
