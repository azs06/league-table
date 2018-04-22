<template>
  <main class="wrapper" id="app">
    <nav-component></nav-component>
    <section class="container">
      <h3>Premier league table</h3>
      <button @click.prevent="fetchTable" class="button" type="button">
        Fetch Table
      </button>
      <hr/>
      <template v-if="standing">
        <table-component :teams="standing"></table-component>
      </template>
    </section>
  </main>
</template>

<script>
const token = "0b0c000e284341998f94eed3a3e62778";
const baseUrl = "http://api.football-data.org/v1";
import NavComponent from './components/NavComponent.vue';
import TableComponent from './components/TableComponent.vue';
import Axios from 'axios';

export default {
  name: 'app',
  data(){
    return {
      standing: null
    }
  },
  components: {
    NavComponent,
    TableComponent
  },
  methods : {
    fetchTable(){
      Axios.get(`${baseUrl}/competitions/445/leagueTable`,{
        headers: {
          'X-Auth-Token': token
        }
      }).then((response) => {
        return response.data
      }).then((result)=>{
        console.log(result)
        this.standing = result.standing;
        console.log(this.standing);
      })
    }
  }
}
</script>

<style>
.wrapper .container {
    max-width: 100rem
}
.wrapper>.container {
    padding-bottom: 7.5rem;
    padding-top: 7.5rem
}
</style>
