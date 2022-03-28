<template>
  <main class="container">
      <div class="row row-cols-1 row-cols-md-2 row-cols-lg-5 g-4 align-items-stretch">
        <card-disc
        v-for="d in filterSearch"
        :key="d.title"
        :disc="d"
        />
    </div>
  </main>
</template>

<script>
import CardDisc from './CardDisc.vue'

export default {
  components: { CardDisc },
  name: 'MainSite',
  props: {
    album: Array,
    genere: String,
    artista: String
  },
  computed: {
    filterSearch () {
      return this.album.filter((item) =>
        item.genre.includes(this.genere) && item.author.includes(this.artista)
      )
    }
  }
}
</script>

<style scoped lang="scss">
</style>
