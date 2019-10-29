<template>
  <v-container>
    <v-layout text-center wrap>
      <v-flex xs12>
        <v-avatar class="my-3" size="120">
          <v-img
            :src="require('../assets/avatar.png')"
            contain
            alt="avatar"
        ></v-img>
        </v-avatar>
        
      </v-flex>

      <v-flex mb-4>
        <h1 class="display-1 font-weight-bold mb-1">
          Omar Saúl Morales Ibarra
        </h1>
        <vue-typer
          class="font-weight-medium"
          :text='positions'
          :repeat='Infinity'
          :shuffle='false'
          initial-action='typing'
          :pre-type-delay='70'
          :type-delay='70'
          :pre-erase-delay='2000'
          :erase-delay='70'
          erase-style='backspace'
          :erase-on-complete='false'
          caret-animation='blink'
        ></vue-typer>
      </v-flex>
    </v-layout>
    <v-row>
      <v-col cols="12" md="12">
        <h2 class="title">Sobre mi</h2>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" md="12">
        <h2 class="title">Proyectos</h2>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" md="12">
        <h2 class="title">Contacto</h2>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
      positions: [
        'Desarrollador Web',
        'Ingeniero en Negocios y Tecnologías de Información',
      ],
      icons: [
        'mdi-home',
        'mdi-email',
        'mdi-calendar',
        'mdi-delete',
      ],
      items: [
        'default',
        'absolute',
        'fixed',
      ],
      padless: false,
      variant: 'default',

  }),
  computed: {
      localAttrs () {
        const attrs = {}

        if (this.variant === 'default') {
          attrs.absolute = false
          attrs.fixed = false
        } else {
          attrs[this.variant] = true
        }
        return attrs
      },
    },
};
</script>
