<template>
  <v-app class="grey lighten-1">
    <BannerHeader title="Home" />
    <v-main>
      <v-container>

        <v-card flat class="my-5 py-5 text-center" color="#1A2238">
          <p class="v-header-text font-weight-light text-h3 text-md-h2">Contact Info:</p>
          <p class="v-header-text font-weight-thin text-h6 text-md-h4">Email: {{ myEmail }} </p>
          <p class="v-header-text font-weight-thin text-h6 text-md-h4">Phone Number: {{ myNumber }}</p>
        </v-card>

        <v-card flat color="#1A2238">
          <h2 class="px-5 pt-3 v-header-text" color="#FF6A3D">Leave me a message:</h2>
          <v-form ref="form" v-model="valid" lazy-validation>
            <v-text-field
              v-model="userName"
              class="px-5 pt-5 v-field"
              outlined
              clearable
              :rules="userNameRules"
              required
              dark
              flat
              color="#FF6A3D"
              label="Your Name"
            >
            </v-text-field>
            <v-text-field
              v-model="userContact"
              class="px-5 v-field"
              outlined
              clearable
              :rules="userContactRules"
              required
              dark
              flat
              color="#FF6A3D"
              label="Phone Number/Email"
            >
            </v-text-field>
            <v-textarea
              v-model="userMessage"
              class="px-5 v-field"
              outlined
              clearable
              :rules="userMessageRules"
              required
              dark
              flat
              color="#FF6A3D"
              label="Message"
            >
            </v-textarea>
            <v-btn outlined class="v-btn mx-5 mb-5" @click="validate" :disabled="!valid">
              Submit
            </v-btn>
          </v-form>
        </v-card>
      </v-container>

      <v-snackbar
        v-model="snackbar"
        color="#FF6A3D"
        timeout="2000"
      >
        {{ snackbarText }} 
        <template v-slot:action="{ attrs }">
          <v-btn
            color="#1A2238"
            text
            v-bind="attrs"
            @click="snackbar = false"
          >
            Close
          </v-btn>
        </template>
      </v-snackbar>
    </v-main>
  </v-app>
</template>

<script>
  import BannerHeader from '../components/BannerHeader'
  import db from '@/fb'
  import { addDoc, collection } from "firebase/firestore"

  export default {
    name: 'qualifications',

    data() {
      return {
        valid: true,
        snackbar: false,
        snackbarText: "",
        select: null,
        userName:"",
        userNameRules: [
          v => !!v || 'Name is required',
        ],
        userContact:"",
        userContactRules: [
          v => !!v || 'Contact is required',
        ],
        userMessage:"",
        userMessageRules: [
          v => !!v || 'Contact is required',
        ],

        myEmail:"rmccauley01@gmail.com",
        myNumber:"405-888-0316",
      }
    },

    components: {
      BannerHeader,
    },

    methods: {

      async validate () {

        if (this.$refs.form.validate()) {

          try{
            const message = await addDoc(collection(db, "messages"), {
              name: this.userName,
              contact: this.userContact,
              message: this.userMessage,
            });

            console.log("Document written with ID: ", message.id)
            this.$refs.form.reset()
            this.snackbarText = "Message sent successfully!"
            this.snackbar = true;
          } catch (e) {
            console.error("Error adding document: ", e);
          }
        }
      },
    }
  }
</script>

<style scoped>
    .v-header-text {
      font-family: 'Lucida Sans';
      color: #FF6A3D;
    }

    .v-btn {
      color: #FF6A3D;
    }

    .v-field {
      border-color: #FF6A3D;
    }
</style>