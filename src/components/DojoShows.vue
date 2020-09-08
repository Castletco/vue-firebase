<template>
  <b-container>
    <div class="hello">
      <h2>{{ msg }}</h2>
      <b-table striped hover :items="shows" :fields="headers"></b-table>
    </div>
    <RegistroShow message="Add a Show" />
  </b-container>
</template>

<script>
import { db } from '@/firebase'
import RegistroShow from '@/components/RegistroShow.vue'
export default {
  name: 'DojoShows',
  props: {
    msg: String
  },
  components: {
    RegistroShow
  },
  data () {
    return {
      shows: [], // to start, the list is empty
      headers: [{ key: 'title', label: 'Titulo', sortable: true },
        { key: 'network', label: 'Plataforma' },
        { key: 'numberOfSeasons', label: 'Temporadas' },
        { key: 'genre', label: 'Género' },
        { key: 'is_current', label: 'Disponible' }]
    }
  },
  firestore () { // adding this key/function
    return {
      shows: db.collection('shows')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
