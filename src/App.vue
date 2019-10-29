<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title>MosaDev</v-list-item-title>
        </v-list-item-content>
        <v-list-item-icon>
          <v-btn icon @click.stop="drawer = !drawer">
            <v-icon>mdi-arrow-left</v-icon>
          </v-btn>
        </v-list-item-icon>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>

        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
        >
<!--           <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon> -->

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar app :collapse-on-scroll='false'>
      <v-app-bar-nav-icon class="d-md-none" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="headline">
        <span>MosaDev</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-toolbar-items class="d-none d-md-flex">
        <v-btn text>sobre mi</v-btn>
        <v-btn text>proyectos</v-btn>
        <v-btn text>contacto</v-btn>
      </v-toolbar-items>
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
    drawer: null,
    items: [
      { title: 'Sobre mi', icon: 'dashboard' },
      { title: 'Proyectos', icon: 'question_answer' },
      { title: 'Contacto', icon: 'question_answer' },
    ],
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
  }),
  methods:{

  }
};
</script>
