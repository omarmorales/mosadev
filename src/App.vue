<template>
  <v-app>
    <SideNav
      :sections="sections"
      :drawer="drawer"
      @toogle="drawer = !drawer"
    />
    <v-app-bar app :collapse-on-scroll="false">
      <v-app-bar-nav-icon
        class="d-md-none"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>
      <v-toolbar-title class="headline">
        <span>MosaDev</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-toolbar-items class="d-none d-md-flex">
        <v-btn v-for="(section, index) in sections" :key="index" text>
          {{ section.title }}
        </v-btn>
      </v-toolbar-items>
    </v-app-bar>

    <v-content>
      <HelloWorld />
    </v-content>

    <v-footer dark padless>
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
import SideNav from "./components/navigation/Sidenav";

export default {
  name: "App",
  components: {
    HelloWorld, SideNav
  },
  data: () => ({
    drawer: false,
    sections: [
      { title: "Sobre mi", icon: "dashboard" },
      { title: "Proyectos", icon: "question_answer" },
      { title: "Publicaciones", icon: "question_answer" },
      { title: "Contacto", icon: "question_answer" }
    ],
    social_networks: [
      {
        icon: "mdi-github-box",
        link: "https://github.com/omarmorales"
      },
      {
        icon: "mdi-linkedin",
        link: "https://www.linkedin.com/in/omar-morales-ibarra-b78b9a7a/"
      },
      {
        icon: "mdi-twitter",
        link: "https://twitter.com/omsamoib"
      }
    ]
  })
};
</script>
