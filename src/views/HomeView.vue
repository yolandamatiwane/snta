<template>
  <div class="home">
    <p v-for="data in getData" :key="data.siteId">
      {{data.price}}
    </p>
  </div>

</template>

<script>
// @ is an alias to /src

export default {
  computed:{
    getData(){
      return this.$store.state.data || []
    }
  },
  methods:{
    getdata(){
      this.$store.dispatch('fetchData')
    }
  },
  mounted() {
  this.getdata()
}


}
</script>
