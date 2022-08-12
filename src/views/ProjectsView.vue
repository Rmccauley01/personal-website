<template>
  <v-app class="grey">
    <BannerHeader title="Home" />
    <v-main>
      <h2 class="v-body-text">
        This is a projects page.
      </h2>
    </v-main>
  </v-app>
</template>

<script>
  import BannerHeader from '../components/BannerHeader'

  export default {
    name: 'qualifications',

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