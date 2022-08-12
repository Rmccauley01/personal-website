<template>
  <v-app class="grey">
    <BannerHeader title="Home" />
    <v-main>
      <v-container fluid flat class="mb-15">
        <h1 class="v-header-text" align="center">
          Resume
          <v-btn depressed class="v-btn mx-3" color="#1A2238" href="RyanMcCauleyResume.pdf" download>
            <v-icon color="#FF6A3D" class="mr-3"> mdi-download </v-icon>
            Download
          </v-btn>
        </h1>

        <v-img class="mx-auto mt-10" :src="resumeSourcePage1" width="1000"> </v-img>

        <v-img class="mx-auto mt-3" :src="resumeSourcePage2" width="1000"> </v-img>

        <h1 class="v-header-text mt-15" align="center">
          Transcript
          <v-btn depressed class="v-btn mx-3" color="#1A2238" href="RyanMcCauleyTranscript.pdf" download>
            <v-icon color="#FF6A3D" class="mr-3"> mdi-download </v-icon>
            Download
          </v-btn>
        </h1>

        <v-img class="mx-auto mt-10" :src="transcriptSourcePage1" width="1000"> </v-img>

        <v-img class="mx-auto mt-3" :src="transcriptSourcePage2" width="1000"> </v-img>
      </v-container>

    </v-main>
  </v-app>
</template>

<script>
  import BannerHeader from '../components/BannerHeader'
  import VuePdfEmbed from 'vue-pdf-embed/dist/vue2-pdf-embed'

  export default {
    name: 'qualifications',

    components: {
      BannerHeader,
      VuePdfEmbed,
    },

    data () {
      return {
        resumeSourcePage1: './resume1.png',
        resumeSourcePage2: './resume2.png',
        transcriptSourcePage1: './transcript1.png',
        transcriptSourcePage2: './transcript2.png',
      }
    }
  }
</script>

<style scoped>
    .v-header-text {
        font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
        color: #1A2238;
        font-weight: "bold";
        margin-left: 2%;
        margin-right: 2%;
    }

    .v-btn {
        color: #FF6A3D;
    }
</style>