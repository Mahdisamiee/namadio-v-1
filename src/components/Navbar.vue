<template>
    <nav>
        <v-toolbar flat class="py-1 px-4">
            <v-toolbar-title class="display-1">
                <v-tooltip right>
                    <router-link to="/" slot="activator">
                        <img  src="../assets/namadio.png" alt="">
                    </router-link>
                    <span class="caption">صفحه اصلی</span>
                </v-tooltip>
            </v-toolbar-title>
            
            <!-- first list -->
            <v-menu offset-y left class="hidden-xs-only">  
                <v-btn flat color="grey darken-1" slot="activator">
                    <span  class="mx-1 body-1">دسته بندی ها</span>
                    <v-icon>arrow_drop_down</v-icon>
                </v-btn>
                <v-list>
                    <v-list-tile avatar v-for="link in links" :key="link.text" router :to="link.route">
                        <v-list-tile-action>
                            <v-icon class="">{{ link.icon }}</v-icon>
                        </v-list-tile-action>
                        <v-list-tile-content>
                            <v-list-tile-title class="caption font-weight-bold">{{ link.text }}</v-list-tile-title>
                        </v-list-tile-content>
                    </v-list-tile>
                </v-list>
            </v-menu>
            <!-- second list -->
            <v-menu offset-y left class="hidden-sm-and-down">  
                <v-btn flat color="grey darken-1" slot="activator">
                    <span class="mx-1 body-1">چطور کار میکند؟</span>
                    <v-icon>arrow_drop_down</v-icon>
                </v-btn>
                <v-list>
                    <v-list-tile avatar v-for="link in links2" :key="link.text" router :to="link.route">
                        <v-list-tile-content>
                            <v-list-tile-title class="caption font-weight-bold">{{ link.text }}؟</v-list-tile-title>
                        </v-list-tile-content>
                    </v-list-tile>
                </v-list>
            </v-menu>
            <v-spacer></v-spacer>
            <!-- sing in -->
            <Signin/>
        </v-toolbar>
    </nav>
</template>

<script>
import Signin from './Signin.vue'

export default {
    components:{
        Signin
    },
    data(){
        return{
            links:[
                { icon:'wb_sunny' , text:'کشاورزی' , route:'/agricalture'},
                { icon:'settings' , text:'صنعتی' , route:'/industrial'},
                { icon:'person' , text:'پوشاک' , route:'/dress'}
            ],
            links2:[
                {text:'پروژه چطور کار  میکند' , route:'/somthing'},
                {text:'مسابقه چطور کار  میکند' , route:'/somthing'},
            ]
        }
    }
}
</script>

<style>

</style>
