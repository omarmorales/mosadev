<template>
  <v-app>
    <SideNav
      :sections="sections"
      :drawer="drawer"
      @toogle="drawer = !drawer"
      :appname="appname"
    />
    <Navbar
      :sections="sections"
      :drawer="drawer"
      @toogle="drawer = !drawer"
      :appname="appname"
    />
    <v-content>
      <transition name="fade" mode="out-in" @after-leave="afterLeave">
        <router-view class="view"></router-view>
      </transition>
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
import SideNav from "./components/navigation/Sidenav";
import Navbar from "./components/navigation/Navbar";

export default {
  name: "App",
  components: {
    SideNav, Navbar
  },
  data: () => ({
    drawer: false,
    appname: "MosaDev",
    sections: [
      { title: "Inicio", route: "/", icon: "dashboard" },
      { title: "Proyectos", route: "/projects", icon: "question_answer" },
      { title: "Publicaciones", route: "/publications", icon: "question_answer" },
      { title: "Contacto", route: "/contact", icon: "question_answer" }
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
  }),
  methods: {
    afterLeave () {
      this.$root.$emit('triggerScroll')
    }
  }
};
</script>
