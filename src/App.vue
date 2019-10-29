<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title class="headline">
        <span>MosaDev</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
    </v-app-bar>

    <v-content>
      <HelloWorld />
    </v-content>

    <v-footer
    dark
    padless
  >
    <v-card
      flat
      tile
      class="indigo lighten-1 white--text text-center"
      min-width="100%"
    >
      <v-card-text col-md>
        <v-btn
          v-for="(social_network, index) in social_networks"
          :key="index"
          class="mx-4 white--text"
          icon
          :href="social_network.link"
          target="_blank"
        >
          <v-icon size="25px">{{ social_network.icon }}</v-icon>
        </v-btn>
      </v-card-text>

      <v-card-text class="white--text pt-0">
        
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>MosaDev</strong>
      </v-card-text>
    </v-card>
  </v-footer>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",
  components: {
    HelloWorld
  },
  data: () => ({
    social_networks: [
      {
        icon: 'mdi-github-box',
        link: 'https://github.com/omarmorales'
      },
      {
        icon: 'mdi-linkedin',
        link: 'https://www.linkedin.com/in/omar-morales-ibarra-b78b9a7a/'
      },
      {
        icon: 'mdi-twitter',
        link: 'https://twitter.com/omsamoib'
      },
    ],
  })
};
</script>
