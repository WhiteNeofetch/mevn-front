<template>
  <div id="app">
    <!--    <router-link to="/">Home</router-link> |-->
    <!--    <router-link to="/about">About</router-link>-->
    <MevnHeader :categories="categories" />
    <Nuxt />
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
import MevnHeader from "../components/layouts/Header.vue";
import {relationMixin} from "@/mixins/relation.mixin";
export default {
  name: "App",
  components: {
    MevnHeader,
  },
    data:()=>({
   
  }),
  async mounted() {
    await this.fetchCategories();
    await this.fetchProducs();
  },
  methods: {
    ...mapActions({
      fetchCategories: "categories/fetchAll",
      fetchProducs: "products/fetchAll",
    }),
  },
  computed: {
    ...mapGetters({
      categories: "categories/items",
       products: "products/items",
    }),
  },
};
</script>

<style >
body,
html {
  padding: 0;
  margin: 0;
  background-color: white;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  /* a {
            font-weight: bold;
            color: #2c3e50;

            &.router-link-exact-active {
                color: #42b983;
            }
        } */
}
</style>
