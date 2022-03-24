<template>
  <header class="position-fixed top-0 start-0 w-100 p-3 d-flex flex-row justify-content-between align-items-center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/7/71/Spotify.png" alt="Spotify logo">
    <div>
        <label for="genere" class="text-uppercase me-3">genere</label>
        <select id="genere">
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Metal">Metal</option>
            <option value="Jazz">Jazz</option>
        </select>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderSite'
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
