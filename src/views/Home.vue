<template>
  <div class="home">
    <DojoShows msg="All Shows"/>
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
