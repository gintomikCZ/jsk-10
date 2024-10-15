<template>
  <nav>
    <ul>
      <li v-for="link in links">
        <RouterLink v-if="$route.path !== link.path" :to="link.path">{{ link.label }}</RouterLink>
        <div v-else>{{ link.label }}</div>
      </li>
    </ul>
    <!-- <div>{{ $route.path }}</div> -->
  </nav>
</template>

<script>

// this.$route - informace o dané route
// this.$router - objekt obsahující routovací metody

export default {
  name: 'TNav',
  props: {
    links: Array
  }
}

</script>
<style scoped>
  nav {
    background: transparent;
  }
  ul {
    list-style-type: none;
    display: flex;
    margin: 0;
    padding: 0;
    gap: 1rem;
  }
  a, div {
    display: block;
    padding: .4em .8em;
  }
</style>