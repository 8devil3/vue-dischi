<template>
  <header class="position-fixed top-0 start-0 w-100 p-3 d-flex flex-row justify-content-between align-items-center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/7/71/Spotify.png" alt="Spotify logo">
    <div class="row g-3">
        <div class="col-auto">
            <label for="genere" class="text-uppercase me-2">genere</label>
            <select id="genere" @change="$emit('selectedGenere', genere)" v-model="genere">
                <option value="">Tutti</option>
                <option v-for="item in arrMenuGenere" :value="item" :key="item">{{ item }}</option>
            </select>
        </div>
        <div class="col-auto">
            <label for="artista" class="text-uppercase me-2">artista</label>
            <select id="artista" @change="$emit('selectedArtista', artista)" v-model="artista">
                <option value="">Tutti</option>
                <option v-for="item in arrMenuArtista" :value="item" :key="item">{{ item }}</option>
            </select>
        </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderSite',
  props: {
    arrMenuGenere: Array,
    arrMenuArtista: Array
  },
  data () {
    return {
      genere: '',
      artista: ''
    }
  }
}
</script>

<style scoped lang="scss">
@import '~bootstrap';

header {
    color: $white;
    background-color: #2E3A46;
    height: 4rem;

    img {
        width: 2rem;
        height: 2rem;
    }
}
</style>
