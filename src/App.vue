<template>
    <div class="container">
        <new-quote v-on:get-quote="quotes.push($event)"></new-quote>
        <quote-grid v-bind:quotes="quotes" v-on:remove-quote="removeQuote($event)"></quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info" v-on:click="showButton=!showButton">Click on a quote to delete it
                                                            <p v-if="showButton"><button>Stress release Button</button></p>
                </div>
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
                showButton:true,
            };
        },
        methods:{
            removeQuote(quoteToDelete){
                this.quotes.splice( this.quotes.indexOf(quoteToDelete), 1);
            }
        },
    }
</script>

<style>
</style>
