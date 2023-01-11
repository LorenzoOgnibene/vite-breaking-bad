<script>
import { store } from '../store';
export default {
    props:{
        cardEl : {
            type : Object,
            required : true
        }
    },
    data(){
        return{
            store,
        }
    }
}
</script>

<template>
    <div class="single-card col py-5">
        <div class="card bg-transparent border-0" style="width: 100%;">
            <img :src="cardEl.card_images[0].image_url" class="card-img-top img-fluid" alt="...">
        <div class="card-body">
            <h5 class="card-title text-white">{{ cardEl.name }}</h5>
            <p class="card-text">{{ cardEl.archetype }}</p>
        </div>
        </div>
    </div>
</template>

<style lang="scss">

</style>