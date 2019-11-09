<template>
    <v-container>
        <v-row>
            <v-col cols=12>
                <v-breadcrumbs :items="breadcrum_items" divider=">"></v-breadcrumbs>
            </v-col>
        </v-row>
        <v-row>
            <v-col cols=12 md=4 v-for="(publication, index) in publications" :key="index">
                <v-hover v-slot:default="{ hover }">
                    <v-card
                        :elevation="hover ? 9 : 2"
                        :href="publication.link"
                        target="_blank"
                    >
                        <v-list-item>
                            <v-list-item-avatar color="grey">
                                <v-img
                                    :src="publication.author.picture"
                                ></v-img>
                            </v-list-item-avatar>
                            <v-list-item-content>
                                <v-list-item-title class="headline">
                                    {{ publication.title }}
                                </v-list-item-title>
                                <v-list-item-subtitle>por <span v-if="publication.author">{{ publication.author.name }}</span></v-list-item-subtitle>
                            </v-list-item-content>
                        </v-list-item>
                        <v-img
                            :src="publication.picture"
                            height="150"
                        ></v-img>
                        <v-card-text>
                            <v-chip class="mr-2" v-for="(tag, index) in publication.tags" :key="index">
                                <v-avatar left>
                                    <v-icon :color="tag.color" v-if="tag.logo_type == 'icon'">
                                        {{ tag.logo }}
                                    </v-icon>
                                    <v-img
                                        v-if="tag.logo_type == 'img'"
                                        src="https://vuejs.org/images/logo.png"
                                    ></v-img>
                                </v-avatar> 
                                {{ tag.name }}
                            </v-chip>
                        </v-card-text>
                    </v-card>
                </v-hover>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
    export default {
        name: "publications",
        data: () => ({
            breadcrum_items: [
                {
                text: 'Inicio',
                disabled: false,
                href: '/',
                },
                {
                text: 'Publicaciones',
                disabled: true,
                href: 'publications',
                },
            ],
            publications: [
                {
                    title: "Create .docx files with Vue.js",
                    link: "https://dev.to/omarmorales/create-docx-files-with-vue-js-3701",
                    author: {
                        name: "Omar Saúl Morales Ibarra",
                        picture: require('../assets/avatar.png')
                    },
                    picture: "https://cdn.vuetifyjs.com/images/cards/mountain.jpg",
                    tags: [
                        {name: "Javascript", logo: "fab fa-js", logo_type: "icon", color: "yellow"},
                        {name: "Vue.js", logo: "fab fa-vuejs", logo_type: "icon", color: "green"}
                    ],
                    active: true,
                    featured: true
                }
            ]
        })
    }
</script>

<style lang="scss" scoped>

</style>