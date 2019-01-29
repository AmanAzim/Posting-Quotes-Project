<template>
    <div class="container">
        <new-quote v-on:get-quote="quotes.push($event)"></new-quote>
        <quote-grid v-bind:quotes="quotes"></quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Click on a quote to delete it</div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    export default {
        components:{
            'quote-grid':QuoteGrid,
            'new-quote':NewQuote,
        },
        data(){
            return{
              quotes:[],
              maxQuotes:10,
            };
        },


    }
</script>

<style>
</style>
