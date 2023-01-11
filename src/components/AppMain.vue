<script>
    import AppCard from './AppCard.vue';
    import axios from 'axios';
    import { store } from '../store'; 
    
    export default{
        components:{
            AppCard
        },
        data(){
            return{
                store,
            }
        },
        methods:{
            getCards(){
                axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0',{
                    params: {

                    }
                })
                .then((response) => {
                    this.store.cardsList = response.data.data;
                    console.log(this.store.cardsList)
                    
                })
                .catch(function (error){
                    console.log(error)
                })
            }
        },
        created(){
            this.getCards();
        }
    }

</script>

<template>
    <div class="main-wrapper">
        <div class="container">
            <div class="row row-cols-lg-5 row-cols-md-3 row-cols-sm-2 d-flex">
                <AppCard v-for="card in store.cardsList" :cardEl="card" />
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    @use '../style/variables' as*;

    .main-wrapper{
        background-color: $main-bg-color;
        width: 100%;
    }
</style>