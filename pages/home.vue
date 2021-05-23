<template>
    <div>
        
    </div>
</template>


<script>
import { mapGetters, mapActions } from "vuex";
import MevnHeader from "../components/layouts/Header.vue";
export default {
  name: "App",
  components: {
    MevnHeader,
  },
    data:()=>({
   
  }),
  async mounted() {
    await this.fetchCategories();
  
  },
  methods: {
    ...mapActions({
      fetchCategories: "categories/fetchAll",
      fetchCategories: "products/fetchAll",
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