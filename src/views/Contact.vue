<template>
    <v-container>
        <v-row>
            <v-col cols="12">
                 <v-breadcrumbs :items="breadcrum_items" divider=">"></v-breadcrumbs>
            </v-col>
        </v-row>
        <v-row id="contact" align="center" justify="center">
            <v-col cols="10" md="6" lg="4">
                <v-card>
                    <v-list-item>
                        <v-list-item-content>
                            <v-list-item-title class="headline text-center text-uppercase">¡Contáctame!</v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>
                    <v-card-text>
                        <v-form
                            ref="form"
                            v-model="valid"
                            :lazy-validation="lazy"
                        >
                            <v-text-field
                                v-model="name"
                                :counter="50"
                                :rules="nameRules"
                                label="Nombre"
                                outlined
                                required
                            ></v-text-field>

                            <v-text-field
                                v-model="email"
                                :rules="emailRules"
                                label="Correo electronico"
                                outlined
                                required
                            ></v-text-field>
                        </v-form>
                    </v-card-text>
                    <v-card-actions>
                        <v-btn text @click="validate">enviar informacion</v-btn>
                        <v-snackbar
                            v-model="snackbar"
                            :timeout="timeout"
                            top
                            right
                        >
                            {{ text }}
                            <v-btn
                                icon
                                @click="snackbar = false"
                            >
                                <v-icon size="20px">fas fa-times-circle</v-icon>
                            </v-btn>
                        </v-snackbar>
                    </v-card-actions>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
    export default {
        name: "contact",
        data: () => ({
            breadcrum_items: [
                {
                    text: 'Inicio',
                    disabled: false,
                    href: '/',
                },
                {
                    text: 'Contacto',
                    disabled: true,
                    href: 'contact',
                },
            ],
            valid: true,
            name: '',
            nameRules: [
                v => !!v || 'Se requiere el nombre',
                v => (v && v.length <= 50) || 'Name must be less than 10 characters',
            ],
            email: '',
            emailRules: [
                v => !!v || 'Se requiere el correo electronico',
                v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
            ],
            lazy: false,
            snackbar: false,
            text: 'Enviado correctamente.',
            timeout: 2000,
        }),
        methods: {
            validate () {
                if (this.$refs.form.validate()) {
                    this.snackbar = true
                    this.clear();
                }
            },
            clear () {
                this.$refs.form.reset()
            },
        },
    }
</script>

<style lang="scss" scoped>

</style>