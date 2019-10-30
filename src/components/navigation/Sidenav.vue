<template>
    <v-navigation-drawer v-model="drawer" absolute temporary>
        <v-list-item>
            <v-list-item-content>
                <v-list-item-title>MosaDev</v-list-item-title>
            </v-list-item-content>
            <v-list-item-icon>
                <v-btn icon @click.stop="toogleDrawer">
                    <v-icon>mdi-arrow-left</v-icon>
                </v-btn>
            </v-list-item-icon>
        </v-list-item>

        <v-divider></v-divider>

        <v-list dense>
            <v-list-item v-for="section in sections" :key="section.title" link>
                <v-list-item-content>
                    <v-list-item-title>{{ section.title }}</v-list-item-title>
                </v-list-item-content>
            </v-list-item>
        </v-list>
    </v-navigation-drawer>
</template>

<script>
    export default {
        props: {
            sections: Array,
            drawer: Boolean
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