<template>
    <div class="row">
        <div class="col-sm-12">
            <h2>Quote added</h2>
            <div class="progress">
                <div class="progress-bar" v-bind:style="{width: pBar + '%'}"></div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props:['pBar'],
        data(){
            return{
            };
        }
    }
</script>

<style scoped>

</style>