<template>
  <v-app class="grey">
    <BannerHeader title="Home" />
    <v-main>
      <v-row>
        <v-col
        cols="12"
        sm="6"
        justify="center"
        class="px-5"
        >
          <v-expansion-panels flat v-model="panels[0]" popout>
            <v-expansion-panel>
              <v-expansion-panel-header color="#1A2238" ripple>
                <v-icon color="#FF6A3D" class="ma-0"> mdi-language-python </v-icon>

                <template v-slot:actions>
                  <v-icon class="v-icon" color="#FF6A3D">
                    $expand
                  </v-icon>
                </template>
              </v-expansion-panel-header>
              <v-expansion-panel-content color="#1A2238">
                <p class="v-body-text text-h6 text-md-h4">
                  {{ projectText[0].title1 }}:
                </p>
                <p class="v-body-text font-weight-thin text-h6 text-md-h4">
                  {{ projectText[0].body1 }}
                </p>

                <p class="v-body-text text-h6 text-md-h4 mt-2">
                  {{ projectText[0].title2 }}:
                </p>
                <p class="v-body-text font-weight-thin text-h6 text-md-h4">
                  {{ projectText[0].body2 }}
                </p>
              </v-expansion-panel-content>
            </v-expansion-panel>
          </v-expansion-panels>
        </v-col>

        <v-col
        cols="12"
        sm="6"
        justify="center"
        class="px-5"
        >
          <v-expansion-panels flat v-model="panels[1]" popout>
            <v-expansion-panel>
              <v-expansion-panel-header color="#1A2238" ripple>
                <v-icon color="#FF6A3D" class="ma-0"> mdi-language-csharp </v-icon>

                <template v-slot:actions>
                  <v-icon class="v-icon" color="#FF6A3D">
                    $expand
                  </v-icon>
                </template>
              </v-expansion-panel-header>
              <v-expansion-panel-content color="#1A2238">
                <p class="v-body-text text-h6 text-md-h4">
                  {{ projectText[1].title }}:
                </p>
                <p class="v-body-text font-weight-thin text-h6 text-md-h4">
                  {{ projectText[1].body }}
                </p>
              </v-expansion-panel-content>
            </v-expansion-panel>
          </v-expansion-panels>
        </v-col>
      </v-row>

      <v-row>
        <v-col
        cols="12"
        sm="6"
        justify="center"
        class="px-5"
        >
          <v-expansion-panels flat v-model="panels[2]" popout>
            <v-expansion-panel>
              <v-expansion-panel-header color="#1A2238" ripple>
                <v-icon color="#FF6A3D" class="ma-0"> mdi-language-javascript </v-icon>

                <template v-slot:actions>
                  <v-icon class="v-icon" color="#FF6A3D">
                    $expand
                  </v-icon>
                </template>
              </v-expansion-panel-header>
              <v-expansion-panel-content color="#1A2238">
                <p class="v-body-text text-h6 text-md-h4">
                  {{ projectText[2].title1 }}:
                </p>
                <p class="v-body-text font-weight-thin text-h6 text-md-h4">
                  {{ projectText[2].body1 }}
                </p>

                <p class="v-body-text text-h6 text-md-h4 mt-2">
                  {{ projectText[2].title2 }}:
                </p>
                <p class="v-body-text font-weight-thin text-h6 text-md-h4">
                  {{ projectText[2].body2 }}
                </p>
              </v-expansion-panel-content>
            </v-expansion-panel>
          </v-expansion-panels>
        </v-col>

        <v-col
        cols="12"
        sm="6"
        justify="center"
        class="px-5"
        >
          <v-expansion-panels flat v-model="panels[3]" popout>
            <v-expansion-panel>
              <v-expansion-panel-header color="#1A2238" ripple>
                <v-icon color="#FF6A3D" class="ma-0"> mdi-cloud </v-icon>

                <template v-slot:actions>
                  <v-icon class="v-icon" color="#FF6A3D">
                    $expand
                  </v-icon>
                </template>
              </v-expansion-panel-header>
              <v-expansion-panel-content color="#1A2238">
                <p class="v-body-text text-h6 text-md-h4">
                  {{ projectText[3].title1 }}:
                </p>
                <p class="v-body-text font-weight-thin text-h6 text-md-h4">
                  {{ projectText[3].body1 }}
                </p>

                <p class="v-body-text text-h6 text-md-h4 mt-2">
                  {{ projectText[3].title2 }}:
                </p>
                <p class="v-body-text font-weight-thin text-h6 text-md-h4">
                  {{ projectText[3].body2 }}
                </p>
              </v-expansion-panel-content>
            </v-expansion-panel>
          </v-expansion-panels>
        </v-col>

      </v-row>
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

    data() {
      return {
        panels: [false, false, false, false],
        projectText: [
          {title1: 'Machine Learning',
           body1: 'Used python and TensorFlow to complete a wide range of machine learning tasks. These included supervised learning, deterministic state machines, decision tree learning, dimensionality reduction, and more. More information on these projects can be found in my resume.',
           title2: 'Data Analytics',
           body2: 'Used python in conjunction with Vue.js and vuetify to retrieve data, display the data, and allow a customer to manipulate the data.'},
          {title: 'Game Development', body: 'Used C# and the Unity game engine to create several games. These games were Asteroid, Flappy Bird, and a game called Scaredy Mage which was created for a Game Jam. These games included full gameplay loops, UI\'s, and user save data.'},
          {title1: 'Data Analytics UI',
           body1: 'Used Vue.js, Vuetify, CSS, and HTML in order to create a UI that allowed users to easily interact with a database. This UI included a data table, filtering options for the user, search fields, and BI graphics. The application consisted of three pages that shared data between them using v-router.',
           title2: 'Personal Website',
           body2: 'Used Vue.js, Vuetify, CSS, and HTML to create this website! For hosting, Google Firebase was used.'},
          {title1: 'Microsoft Azure',
           body1: 'Used Power Automate in order to create a flow that automated a previously manual process that took roughly 3 hours per day for each of the 6 employees engaged in load board bidding. The flow reduced the amount of time to complete this task to 15 minutes per employee per day which allowed for the reduction or relocation of 1 FTE.',
           title2: 'Google Firebase',
           body2: 'Used Google Firebase hosting and Firestore in order to host and store data for this site. Firestore is used to store the messages that can be sent on the Contact Me page.'},
        ],
      }
    },
  }
</script>

<style scoped>
    .v-body-text {
        font-family: 'Lucida Sans';
        color: #FF6A3D;
    }

    .v-btn {
        color: #FF6A3D;
    }

    .v-icon {
      color: #FF6A3D;
      font-size: 96px;
    }
</style>