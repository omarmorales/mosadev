<template>
    <v-container>
        <v-row>
            <v-col cols="12">
                 <v-breadcrumbs :items="breadcrum_items" divider=">"></v-breadcrumbs>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
    export default {
        name: "projects",
        data: () => ({
            breadcrum_items: [
                {
                    text: 'Inicio',
                    disabled: false,
                    href: '/',
                },
                {
                    text: 'Proyectos',
                    disabled: true,
                    href: 'projects',
                },
            ],
        })
    }
</script>

<style lang="scss" scoped>

</style>