<template>
    <div class="row">
        <quote v-for="x in quotes" v-on:click.native="deleteQuote(x)">{{x}}</quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue'
    export default {
        components:{
            'quote':Quote,
        },
        props:['quotes'],
        methods:{
            deleteQuote(quoteRemove){
                this.$emit('remove-quote', quoteRemove);
            }
        }
    }
</script>

<style scoped>

</style>