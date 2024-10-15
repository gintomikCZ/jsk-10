<template>
  <TNav :links="links"/>
  <RouterView />
  <button @click="onClick('/')">home</button>
  <button @click="onClick('/about')">about me</button>
  <button @click="onClick('/contact')">contact</button>
</template>

<script>
import TNav from '@/components/TNav.vue'
export default {
  name: 'App',
  data () {
    return {
      links: [
        { path: '/', label: 'home' },
        { path: '/about', label: 'about me' },
        { path: '/contact', label: 'contact' }
      ]
    }
  },
  methods: {
    onClick (path) {
      this.$router.push(path)
      /*
        this.$router.push (path) - přesměruje na path
        this.$router.back() - o jednu zpět v historii
        this.$router.forward() - o jednu vpřed v historii
        this.$router.go(n) - o n vpřed v historii
        this.$router.go(-n) - o n vzad v historii
      */
    }
  },
  components: { TNav }
}

</script>
