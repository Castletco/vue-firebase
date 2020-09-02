<template>
  <div>
    <ul>
      <li v-for="(pelicula, index) in peliculas" v-bind:key="index">{{ pelicula }}</li>
    </ul>
  </div>
</template>

<script>
import { db } from '@/firebase'
export default {
  name: 'Peliculas',
  data () {
    return {
      peliculas: [] // to start, the list is empty
    }
  },
  firestore () { // adding this key/function
    return {
      peliculas: db.collection('peliculas')
    }
  }
}

</script>

<style scoped>

</style>
