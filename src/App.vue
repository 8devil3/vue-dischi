<template>
  <div id="app">
    <header-site />
    <main-site />
  </div>
</template>

<script>
import HeaderSite from './components/HeaderSite.vue'
import MainSite from './components/MainSite.vue'

export default {
  name: 'App',
  components: {
    HeaderSite,
    MainSite
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
    justify-content: center;

    a {
        text-decoration: none;
    }
}

</style>
