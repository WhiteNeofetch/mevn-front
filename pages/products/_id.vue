<template>
    <div>
        {{this.item.title}}
           <img :src="this.item.image" alt="" />
           {{this.item.description}}
           {{this.item.price}}
           {{this.item.amount}}
           {{this.item.categories}}
           
    </div>
</template>


<script>
import { mapGetters, mapActions } from "vuex";
import MevnHeader from "../../components/layouts/Header.vue";
export default {
  name: "App",
  components: {
    MevnHeader,
  },
    data:()=>({
   
  }),
  async mounted() {
    await this.fetchItem(this.$route.params.id)
  console.log(this.item)
  },
  methods: {
    ...mapActions({
         fetchItem: `products/fetchOne`,
    }),
  },
  computed: {
    ...mapGetters({
       item:`products/item`,
    }),
  },
};
</script>