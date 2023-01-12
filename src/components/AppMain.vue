<script>
    import axios from 'axios';
    import { store } from '../store'; 
    
    import AppCard from './AppCard.vue';
    import AppSelect from './AppSelect.vue';
    
    export default{
        components:{
            AppCard,
            AppSelect,  
        },
        data(){
            return{
                store,
                apiUrl : 'https://db.ygoprodeck.com/api/v7/cardinfo.php',
                
            }
        },
        methods:{
            getCards(){
                axios.get(this.apiUrl,{
                    params: {
                        archetype : store.arcTypeVal,
                        num : 10,
                        offset : 0,
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
        <AppSelect />
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