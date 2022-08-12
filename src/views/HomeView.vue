<template>
  <v-app class="grey">
    <BannerHeader title="Home" />
    <v-main>
      <h2 class="v-body-text">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Illo tempore quam vitae. Quo harum explicabo et aliquid ex id consequatur eaque, minima asperiores quis? Enim eaque ipsam dolor qui aut?
      </h2>
    </v-main>
  </v-app>
</template>

<script>
  import BannerHeader from '../components/BannerHeader'

  export default {
    name: 'home',

    components: {
      BannerHeader,
    },
  }
</script>

<style scoped>
    .v-body-text {
        font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
        color: #1A2238;
        margin-left: 2%;
        margin-right: 2%;
    }

    .v-btn {
        color: #FF6A3D;
    }
</style>