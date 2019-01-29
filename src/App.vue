<template>
    <div class="container">

        <quote-grid v-bind:quotes="quotes"></quote-grid>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';

    export default {
        components:{
            'quote-grid':QuoteGrid,

        },
        data(){
            return{
              quotes:['test quote'],
              maxQuotes:10,
            };
        },


    }
</script>

<style>
</style>
