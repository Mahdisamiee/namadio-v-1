<template>
    <nav>
        <v-toolbar  flat class="py-1 px-4">
            <v-toolbar-side-icon @click="drawer = !drawer" left></v-toolbar-side-icon>
            <v-spacer></v-spacer>
            <v-toolbar-title>
                <router-link to="/" slot="activator">
                    <img  src="../assets/namadio.png" alt="">
                </router-link>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <div class="shortcut-icon">
                <v-layout row>
                    <v-flex xs12>
                        <v-btn icon flat color="grey darken-1">
                            <v-icon>add</v-icon>
                        </v-btn>
                    </v-flex>
                    <v-flex xs12>
                        <v-btn icon flat color="grey darken-1">
                            <v-icon>chat_bubble_outline</v-icon>
                        </v-btn>
                    </v-flex>
                </v-layout>
            </div>
        </v-toolbar>

        <v-navigation-drawer right v-model="drawer" app dark class="lighten-3">
            <div class="personinfo success lighten-1">
                <v-layout class="grey darken-3 py-2 px-3 my-3 ml-1 white--text" row wrap>
                    <v-flex xs6>
                        <v-avatar
                            size="65"
                            color="blue darken-1"
                        >
                            <img v-if="person.img" :src="person.img">
                            <span v-if="!person.img">{{person.name}}</span>
                        </v-avatar>
                    </v-flex>
                    <v-flex xs6>
                        <h3>{{person.name}} {{person.lastname}}</h3>
                        <span class="caption">
                            {{person.status}}
                            <v-icon small left>build</v-icon>
                        </span>
                    </v-flex>
                </v-layout>
            </div>
            <!-- **this stuff should be change to that i want -->
            <v-list>
                <v-list-tile dark v-for="item in items" :key="item.title" avatar router :to="item.route">
                    <v-list-tile-action>
                        <v-icon >{{item.icon}}</v-icon>
                    </v-list-tile-action>
                    <v-list-tile-content class="mr-0 caption">
                        <v-list-tile-title class="white--text">
                            {{item.text}}
                        </v-list-tile-title>
                    </v-list-tile-content>

                    
                </v-list-tile>
            </v-list>
        </v-navigation-drawer>
    </nav>
</template>

<script>
export default {
    data(){
        return{
            drawer: false,
            items: [
                { icon:'home' , text:'صفحه اصلی' , route:'/'},
                { icon:'folder' , text:'محصولات' , route:'/products'},
                { icon:'person' , text:'تیم ما' , route:'/team'},
                { icon:'home' , text:'صفحه اصلی' , route:'/'},
            ],
            person: {
                img:"",
                name: "Mahdi",
                lastname: "samiee",
                status: "تولید کننده"
            }
        }
    }
}
</script>

<style>

</style>
