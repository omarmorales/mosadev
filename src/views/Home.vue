<template>
    <v-container>
        <v-row class="h-90" align="center" justify="center">
            <v-col cols="12" md="12">
                <v-layout text-center wrap >
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
                        <h1 class="display-2 font-weight-bold mb-1">
                            Omar Saúl Morales Ibarra
                        </h1>
                        <vue-typer
                            class="headline"
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
            </v-col>
        </v-row>
        
        <v-row>
            <v-col cols="12" md="12">
                <h2 class="display-1 text-uppercase font-weight-bold mb-3">Sobre mi</h2>
                <p class="font-weight-bold">
                    Soy un <span class="indigo--text text--lighten-1">desarrollador web</span> con más de <span class="indigo--text text--lighten-1">5 años de experiencia</span>, nacido en San Luis Potosí y actualmente viviendo en la Ciudad de México.
                </p>
                <p>
                    <span class="font-weight-bold">He desarrollado, lanzado y mantenido múltiples proyectos desde cero</span> tanto en la parte de back-end como front-end.
                </p>
                <p>Las herramientas con las que trabajo actualmente son:</p>

            </v-col>
        </v-row>
        <v-row>
            <v-col cols="12" md="12">
                <h2 class="display-1 text-uppercase font-weight-bold mb-3"><i class="fas fa-graduation-cap"></i> Educacion</h2>
                <v-timeline dense>
                    <v-timeline-item
                        class="mb-4"
                        color="white"
                        fill-dot
                    >
                        <template v-slot:icon>
                            <v-avatar>
                                <img 
                                    :src="require('../assets/itesm-logo.jpeg')"
                                >
                            </v-avatar>
                        </template>
                        <v-row class="pt-1">
                            <v-col cols="12" md="3" lg="2">
                                <strong>2012 - 2016</strong>
                            </v-col>
                            <v-col>
                                <p class="font-weight-bold mb-0">Instituto Tecnológico y de Estudios Superiores de Monterrey (ITESM)</p>
                                <p class="mb-0">Ingenieria en Negocios y Tecnologias de Informacion</p>
                            </v-col>
                        </v-row>
                    </v-timeline-item>
                </v-timeline>
            </v-col>
        </v-row>
        <v-row>
            <v-col cols="12" md="12">
                <h2 class="display-1 text-uppercase font-weight-bold mb-3"><i class="fas fa-award"></i> Cursos y certificaciones</h2>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    name: "home",
    props: {
        contact_selected: Boolean
    },
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
    methods: {
        
    },
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