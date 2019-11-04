<template>
    <v-app-bar app>
        <v-app-bar-nav-icon
            class="d-md-none"
            @click.stop="toogleDrawer"
        ></v-app-bar-nav-icon>
        <v-toolbar-title class="headline">
            <span>{{ appname }}</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn icon>
            <v-icon>mdi-magnify</v-icon>
        </v-btn>
        <v-toolbar-items class="d-none d-md-flex">
            <v-btn :to="section.route" v-for="(section, index) in sections" :key="index" text>
                {{ section.title }}
            </v-btn>
        </v-toolbar-items>
    </v-app-bar>
</template>

<script>
    export default {
        props: {
            sections: Array,
            drawer: Boolean,
            appname: String
        },
        methods: {
            toogleDrawer(){
                this.$emit('toogle', true)
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>