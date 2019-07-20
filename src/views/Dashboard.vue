<template>
    <main>
        <navbar2/>
        <v-content>
            <v-container grid-list-lg class="blue-grey--text text--darken-2 mt-3">
                <v-layout row wrap>
                    <v-flex xs12 class="mb-2">
                        <span class="subheading">
                            <div>فعالیت های تولیدی و ارائه خدمات</div>
                        </span>
                    </v-flex>
                    <v-flex xs12 md4 v-for="card in cards" :key="card.title">
                        <div class="main-card">
                            <div class="num-icon">
                                <span>{{card.number}}</span>
                                <span class="body-2" v-if="card.numberadd">{{card.numberadd}}</span>
                                <v-spacer></v-spacer>
                                <v-icon icon class="green--text text--accent-4">{{card.icon}}</v-icon>
                            </div>
                            <div class="card-title">
                                <span>{{card.title}}</span>
                            </div>
                            <div class="card-link">
                                <router-link :to="card.link">مشاهده</router-link>
                            </div>
                        </div>
                    </v-flex>
                </v-layout>
            </v-container>
        </v-content>
    </main>
</template>

<script>
import Navbar2 from "../components/Navbar2.vue"
export default {
    components:{
        Navbar2
    },
    data(){
        return{
            card:{number:"220",title:"آگهی با مهارت های من",link:"/projects/ability"},

            cards:[
                {number:"220",title:"آگهی با مهارت های من",link:"/projects/ability",icon:"class"},
                {number:"20",title:"آگهی با تولیدات من",link:"/projects/product",icon:"build"},
                {number:"220",title:"آن",link:"/projects",icon:"3d_rotation"},
                {number:"2",title:"نمونه کارها",link:"/projects/samples",icon:"folder"},
                {number:"10",title:"دنبال کنندگان من",link:"/projects/followers",icon:"favorite"},
                {number:"220",numberadd:"ریال",title:"موجودی من",link:"/projects/bankacount",icon:"euro_symbol"},
            ]
        }
    }
}
</script>

<style>
    div.line{
        outline: 1px solid black;
        border: none;
    }
    div.main-card{
        display: flex;
        flex-direction: column;
        min-height: 90%;
        border: 1px solid grey;
        border-radius: 2px;
        padding: 7px;
        margin: 20px 0px;
    }
    div.main-card > div{
        margin: 5px 0px;
    }
    div.main-card .num-icon{
        display: flex;
        justify-content: space-between;
        font-size: 30px;
    } 
    div.main-card .num-icon .v-icon{
        font-size: 40px;
    }
    div.main-card .card-link a{
        text-decoration: none;
        color: green;
        font-size: 12px;
    }
    div.main-card .card-link a:hover{
        color: rgb(18, 185, 18)
    }
</style>
