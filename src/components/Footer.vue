<template>
    <v-footer
        dark
        height="auto"
    >
        <v-card
            class="flex"
            flat
            tile
        >
            <v-card-title class="green ">
                <strong class="subheading">ما را در شبکه های اجتماعی دنبال کنید!</strong>

                <v-spacer></v-spacer>

                <v-btn
                    v-for="icon in icons"
                    :key="icon"
                    class="mx-3"
                    dark
                    icon
                >
                <v-icon size="24px">{{ icon }}</v-icon>
                </v-btn>
            </v-card-title>

            <v-card-actions class="grey darken-3 justify-center">
                2019 all right are reserved by Nanova— <strong>Namadio</strong>
            </v-card-actions>
        </v-card>
    </v-footer>
</template>

<script>
export default {
    data(){
        return{
            icons: [
                'fab fa-facebook',
                'fab fa-twitter',
                'fab fa-google-plus',
                'fab fa-linkedin',
                'fab fa-instagram'
            ]
        }
    }
}
</script>

<style>

</style>
