<template>
  <v-app class="grey lighten-1">
    <BannerHeader title="Home" />
    <v-main class="mb-15">
      <v-container>
        <v-carousel
          height="100%"
          hide-delimiter-background
          show-arrows-on-hover
        >

          <v-carousel-item>
            <v-sheet
              color="#1A2238"
              height="100%"
            >
              <v-row
                justify="center"
              >
                <div class="v-body-text text-h3 text-md-h2 mt-12">
                  About Me
                </div>
              </v-row>

              <v-row justify="center" class="mt-10">
                <v-img class="mx-10" contain aspect-ratio="3" :src="bigmanoncampus"></v-img>
              </v-row>

              <v-row justify="center" class=" text-body mx-12 mb-12 ">
                <h2 class="v-body-text ma-12 mb-12 font-weight-thin text-h6 text-md-h4">
                  Hello, My name is Ryan McCauley and I am a Senior Computer Science major at Texas A&M University. My anticipated graduation date is May 2023. I am seeking a position upon graduation where I can broaden my knowledge and put my skills to work. Aside from working on school, I enjoy taking up personal coding projects (like this one), playing rugby for A&M, exploring entrepreneurial ideas, and several other hobbies. Please browse this site for my resume and other information. 
                </h2>
              </v-row>

            </v-sheet>
          </v-carousel-item>

          <v-carousel-item
            v-for="(slide, i) in slides"
            :key="i"
          >
            <v-sheet
              color="#1A2238"
              height="100%"
            >
              <v-row
                justify="center"
              >
                <div class="v-body-text text-h3 text-md-h2 mt-12">
                  {{ slide }}
                </div>
              </v-row>

              <v-row justify="center" class="mt-10">
                <v-icon class="v-icon" ma-0>
                  {{ icons[i] }}
                </v-icon>
              </v-row>

              <v-row justify="center" class=" text-body mx-12 mb-12 ">
                <h2 class="v-body-text ma-12 mb-12 font-weight-thin text-h6 text-md-h4">
                  {{ bodyText[i] }}
                </h2>
              </v-row>

            </v-sheet>
          </v-carousel-item>
        </v-carousel>
      </v-container>
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

    data() {
      return {
        slides: [
          'Skills',
          'Hobbies',
          'Interests',
          'Roadmap',
        ],
        icons: [
          'mdi-code-braces-box',
          'mdi-sprout',
          'mdi-rocket-launch',
          'mdi-road-variant',
        ],
        bodyText: [
          'Through work experience and school projects I have developed a broad coding skillset including C++, python, C#, Java, and more. In addition to this, I work as a full stack web developer and work with cloud environments (Microsoft Azure and Google Firebase). Finally, leadership, public speaking, and entrepreneurial skills mean I am well rounded beyond developing.',
          'When I am not working or attending classes I enjoy several different hobbies. First and foremost, I love staying physically fit and competitive through weight lifting and rugby. Secondly, I am an avid gardener... I currently have my apartment crammed with 25 plants. Lastly, I love spending time outside, whether it is at the beach or in the mountains.',
          'As we move towards the future, I think that there are several fields that will inevitably impact this world for the better. I see space flight, ML/AI, data analytics, and renewables all contributing immensely to human growth and prosperity. It is my goal in life to drive any number of these technologies forward because I believe it is the best way for me to contribute.',
          'Ten years from now my hope is to be working a job I love in one of the fields I mentioned previously. I hope to have a family, a yard where my plants can finally roam free, and to still be learning skills/technologies to ensure I do not fall behind.',
        ],
        bigmanoncampus: './bIgMaNoNcAmPuS.png',
      }
    },
  }
</script>

<style scoped>
    .v-body-text {
        font-family: 'Lucida Sans',;
        color: #FF6A3D;
    }

    .v-btn {
        color: #FF6A3D;
    }

    .v-icon {
      color: #FF6A3D;
      font-size: 144px;
    }
</style>