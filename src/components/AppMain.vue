<script>
    import AppCard from './AppCard.vue'
    import axios from 'axios';
    export default{
        components:{
            AppCard
        },
        data(){
            return{
                test:[],
               
            }
        },
        methods:{
            getCards(){
                axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0',{
                    params: {

                    }
                })
                .then((response) => {
                    this.test = response.data.data;
                    console.log(this.test)
                    
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
        <div v-for="card in test">
            <AppCard :cardDetails="card.card_images[0].image_url"/>
        </div>
    </div>
</template>

<style lang="scss">
    .main-wrapper{
        background-color: #d48f38;
        width: 100%;
        height: 100vh;
        
    }
</style>