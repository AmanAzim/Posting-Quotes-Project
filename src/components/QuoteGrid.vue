<template>
    <div class="row">
        <quote v-for="x in quotes">{{x}}</quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue'
    export default {
        components:{
            'quote':Quote,
        },
        props:['quotes'],
    }
</script>

<style scoped>

</style>