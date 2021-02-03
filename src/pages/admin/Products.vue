<template>
  <div class="table-responsive">
    <table class="table table-striped table-sm">
      <thead>
        <tr>
          <th>#</th>
          <th>Image</th>
          <th>Title</th>
          <th>Likes</th>
          <th>Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="product in products" :key="product.id">
          <td>{{ product.id }}</td>
          <td><img :src="product.img" height="350" /></td>
          <td>{{ product.mark }}</td>
          <td>{{ product.model }}</td>
          <td></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import { ref, onMounted } from "vue";
export default {
  name: "Products",
  setup() {
    const products = ref([]);

    onMounted(async () => {
      const response = await fetch("http://api.mocki.io/v1/1443ee19");

      products.value = await response.json();
     console.log(products)
    });

    return {
      products,
    };
  },
};
</script>

<style lang="scss" scoped></style>
