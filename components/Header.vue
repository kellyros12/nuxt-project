<template>
  <b-navbar toggleable="lg" type="dark" variant="info">
    <b-navbar-brand href="#">Movie Lookup!</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item
          v-for="navLink in navLinks"
          v-bind:key="navLink.id"
          :href="navLink.urlPath"
        >
          {{ navLink.name }}
        </b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>


<script>
  export default {
    name: 'my-header',
    components: {},
    props: {
      show: Boolean,
      function: Function,
      query: String,
    },
    data() {
      return {
        navLinks: [
          { id: 1, urlPath: '/', name: 'Home' },
          { id: 2, urlPath: '/favorites', name: 'Favorites' },
        ],
      }
    },
    computed: {
    },
    methods: {
  },
  }
</script>

<style lang="scss">

</style>
