<template>
    <div class="container">

        <header-bar v-bind:pBar="pBar" v-bind:maxQuotes="maxQuotes" v-bind:arrLen="quotes.length"></header-bar>

                    <!-- v-on:get-quote="quotes.push($event)" -->
        <new-quote v-on:get-quote="addQuote($event)"></new-quote>

        <quote-grid v-bind:quotes="quotes" v-on:remove-quote="removeQuote($event)"></quote-grid>

        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info" v-on:click="showButton=!showButton" >
                    <p v-if="quotes.length!==maxQuotes">Click on a quote to delete it</p>
                    <p v-else>Delete some quotes to add more</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import Header from './components/Header.vue';

    export default {
        components:{
            'quote-grid':QuoteGrid,
            'new-quote':NewQuote,
            'header-bar':Header,
        },
        data(){
            return{
                quotes:[],
                maxQuotes:10,
                showButton:true,
                pBar:0,
            };
        },
        methods:{
            addQuote($event){
                if(this.quotes.length==this.maxQuotes){
                    return;
                }
                else{
                    this.quotes.push($event);
                    this.pBar+=10;
                }

            },
            removeQuote(quoteToDelete){
                this.quotes.splice( this.quotes.indexOf(quoteToDelete), 1);
                this.pBar-=10;
            },
        },
    }
</script>

<style>
</style>
