<template>
    <nav>
        <v-app-bar app color="#1A2238">
            <v-container fluid>
                <v-row
                    align="center"
                >
                    <v-menu offset-y>
                        <template v-slot:activator="{ on, attrs }">
                            <v-btn text class="mr-3 ml-0 hidden-lg-and-up" v-bind="attrs" v-on="on">
                                <v-icon color="#FF6A3D">mdi-menu</v-icon>
                            </v-btn>
                        </template>
                        <v-list color="#1A2238">
                            <v-list-item v-for="tab in tabs" :key="tab.name">
                                <v-btn text class="v-btn" router :to="tab.route">
                                    {{ tab.name }}
                                </v-btn>
                            </v-list-item>
                        </v-list>
                    </v-menu>

                    <h1 class="v-title">
                        RYAN D. MCCAULEY
                    </h1>

                    <v-spacer></v-spacer>

                    <v-btn text class="v-btn hidden-md-and-down" v-for="tab in tabs" :key="tab.name" router :to="tab.route">
                        {{ tab.name }}
                    </v-btn>

                    <v-spacer></v-spacer>
                </v-row>
            </v-container>
        </v-app-bar>
    </nav>
</template>

<script>
import { onMounted } from 'vue'
    export default {
        props: ['title'],

        data () {
            return {
                tabs: [
                    {name: "Home", route: "/"},
                    {name: "Qualifications", route: "/qualifications"},
                    {name: "Projects", route: "/projects"},
                    {name: "Contact", route: "/contact"}
                ],
            }
        },

        methods: {

        },

        computed: {

        }
    }
</script>

<style scoped>
    .v-title {
        font-weight: bold;
        font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
        color: #FF6A3D;
    }

    .v-btn {
        color: #FF6A3D;
        margin: 2%;
    }
</style>