<template>
    <div class="row">
       <form>
         <div class="col-xs-12 col-sm-8 col-md-6 col-sm-offset-2 col-md-offset-3 form-group">
             <label>Quote</label>
             <textarea class="form-control" rows="3" v-model="quote"></textarea>
         </div>

           <div class="col-xs-12 col-sm-8 col-md-6 col-sm-offset-2 col-md-offset-3 form-group">
               <button class="btn btn-primary" v-on:click.prevent="createNew">Add Quote</button>
           </div>
       </form>
    </div>
</template>

<script>
    export default {
        data(){
            return{
              quote:'',
            };
        },
        methods:{
            createNew(){
                if(this.quote==''){ return;}

                this.$emit('get-quote', this.quote);
                this.quote='';
            },
        }
    }
</script>

<style scoped>

</style>