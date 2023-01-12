<script>
import { store } from '../store';

export default {
    name: 'AppSelect',

    data(){
        return{
            store, 
            currentSel : ' ' ,
            newVal : store.arcTypeVal,
            
        }
    }
}
</script>


<template>
    <div class="select-wrapper">
        <select v-model="currentSel" >
            <option value="Alien">Alien</option>
            <option value="Laval">Laval</option>
            <option value="Vylon">Vylon</option>
            <option value="Inzektor">Inzektor</option>
            <option value="Umi">Umi</option>
            <option value="Gusto">Gusto</option>
        </select>
    </div>
</template>

<style lang="scss">
    
</style>