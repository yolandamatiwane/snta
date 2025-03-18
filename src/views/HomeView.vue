<template>
  <div class="home">

    <table class="table">
      <thead>
        <tr>
          <th scope="col">Category</th>
          <th scope="col">Full Name</th>
          <th scope="col">Price</th>
          <th scope="col">Move</th>
          <th scope="col">Pmove</th>
          <th scope="col">Date & Time</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="data in getData" :key="data.siteId">
          <td>{{ data.categoryName }}</td>
          <td>{{ data.fullName }}</td>
          <td>{{ data.price }}</td>
          <td>{{ data.move }}</td>
          <td>{{ data.pmove }}</td>
          <td>{{ data.datetime }}</td>
        </tr>
      </tbody>
    </table>

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
