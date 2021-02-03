<template>
  <div>
    <Nav />>
    <div class="container-fluid">
      <div class="row">
        <Menu />
        <main role="main" class="col-md-9 ml-sm-auto col-lg-10 pt-3 px-4">
          <router-view />
        </main>
      </div>
    </div>
  </div>
</template>

<script>
import Nav from "@/components/Nav";
import Menu from "@/components/Menu";
// import Products from './Products.vue';
export default {
  name: "Admin",
  components: {
    Nav,
    Menu,
    // Products
  },
};
</script>
