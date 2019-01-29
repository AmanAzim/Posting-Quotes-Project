<template>
    <div class="row">
        <div class="col-sm-12">
            <h2>Quote added</h2>
            <div class="progress">    <!--v-bind:style="{width: (arrLen*10) + '%'}" -->
                <div class="progress-bar" v-bind:style="{width: pBar + '%'}">{{arrLen}} / {{maxQuotes}}</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props:['pBar', 'maxQuotes', 'arrLen'], // we actually need only pBar or arrLen, one of them is enough
        data(){
            return{
            };
        }
    }
</script>

<style scoped>

</style>