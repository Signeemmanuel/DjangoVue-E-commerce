<template>
  <div class="home p-4">
    <section class="bg-slate-900 h-80 flex justify-center align-middle">
      <div class="flex flex-col justify-center align-middle gap-4">
        <h1 class="text-4xl text-white text-center">Welcome to E-commerce</h1>
        <p class="text-slate-100 text-center">
          The best E-commerce store online
        </p>
      </div>
    </section>
    <section class="my-8">
      <div>
        <h2 class="text-5xl text-center">Latest Products</h2>
      </div>
      <article class="my-4 flex flex-wrap gap-4">
        <div v-for="product in latestProducts" :key="product.id">
          <div class="border rounded-lg shadow-xl">
            <figure class="image">
              <img :src="product.get_thumbnail" />
            </figure>

            <div class="p-2">
              <h3 class="text-lg font-bold">{{ product.name }}</h3>
              <p >${{ product.price }}</p>
              
              <p class="text-slate-700 cursor-pointer">view detials</p>
            </div>
          </div>
        </div>
      </article>
    </section>
  </div>
</template>

<script>
export default {
  name: "HomeView",
  inject: ["axios"],
  data() {
    return {
      latestProducts: [],
    };
  },

  mounted() {
    this.getLatestProducts();
  },

  methods: {
    getLatestProducts() {
      this.axios
        .get("/products/latest-products/")
        .then((response) => {
          this.latestProducts = response.data;
          console.log(this.latestProducts);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>
