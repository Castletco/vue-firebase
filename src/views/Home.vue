<template>
  <div class="home">
    <DojoShows msg="All Shows"/>
    <h1>Pendiente</h1>
  </div>
</template>

<script>
// @ is an alias to /src
import DojoShows from '@/components/DojoShows.vue'

export default {
  name: 'Home',
  components: {
    DojoShows
  }
}
</script>
