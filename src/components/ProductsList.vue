<template>
    <div v-if="products.length">
         <paginate 
            name="products"
            :list="products"
            :per="perPage"
        >
    </div>
    <b-alert v-else show variant="info">No hay productos que mostrar</b-alert>
</template>

<script>
import {mapActions,mapMutations, mapState} from 'vuex';

export default {
    mounted(){
            this.fetchProducts();
    },
    data(){
        return {
            paginate:['products'],
            perPage: 3
        }
    },
    computed:{
        ...mapState('products',['products'])
    },
    methods:{
        ...mapActions('products',['fetchProducts'])
    }

}
</script>