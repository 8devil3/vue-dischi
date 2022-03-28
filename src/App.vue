<template>
  <div id="app">
    <header-site @selectedGenere="setGenere" @selectedArtista="setArtista" :arrMenuGenere="menuItemsGenere" :arrMenuArtista="menuItemsArtista"/>
    <main-site :genere="gen" :artista="art" :album="arrDiscs"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeaderSite from './components/HeaderSite.vue'
import MainSite from './components/MainSite.vue'

export default {
  name: 'App',
  components: {
    HeaderSite,
    MainSite
  },
  data () {
    return {
      baseURL: 'https://flynn.boolean.careers/exercises/api/array/',
      arrDiscs: [],
      menuItemsGenere: [],
      menuItemsArtista: [],
      gen: '',
      art: ''
    }
  },
  methods: {
    setGenere (argomento) {
      this.gen = argomento
    },
    setArtista (argomento) {
      this.art = argomento
    },
    getData () {
      axios.get(`${this.baseURL}music`)
        .then((response) => {
          this.arrDiscs = response.data.response
          this.getMenuSelect()
        })
    },
    getMenuSelect () {
      this.menuItemsGenere = [...new Set(this.arrDiscs.map(item => item.genre))]
      this.menuItemsArtista = [...new Set(this.arrDiscs.map(item => item.author))]
    }
  },
  created () {
    this.getData()
  }
}
</script>

<style lang="scss">
@import '~bootstrap';

#app {
    background-color: #1E2D3B;
    height: 100%;
    min-height: 100vh;
    padding: 6rem 1rem 2rem 1rem;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;

    a {
        text-decoration: none;
    }
}

</style>
