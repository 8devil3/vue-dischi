<template>
<a href="" class="col d-block">
  <article class="text-center h-100 p-3">
    <img :src="disc.poster" :alt="disc.title" class="w-100 mb-2">
    <h2 class="h6 text-uppercase">{{ disc.title }}</h2>
    <p class="m-0">{{ disc.author }}</p>
    <p class="m-0">{{ disc.year }}</p>
  </article>
</a>
</template>

<script>
export default {
  name: 'CardDisc',
  props: {
    disc: Object
  }
}
</script>

<style scoped lang="scss">
@import '~bootstrap';

article {
    color: $white;
    background-color: #2E3A46;
    text-decoration: none;

    &:hover {
        color: $gray-200;
        background-color: $gray-700;
    }

    p {
        color: $gray-500;
    }
}
</style>
