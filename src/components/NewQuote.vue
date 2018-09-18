<template>
    <div class="row">
        <div class=" col-md-offset-3 col-md-6">
            <form class="form-horizontal">
                <div class="form-group">
                    <label>Quote</label>
                    <textarea class="form-control" rows="3" v-model="quote"></textarea>
                </div>
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
            </form>
        </div>
    </div>
</template>

<script>
  export default {
    data: function(){
      return {
        quote: ''
      }
    },
    methods: {
      createNew() {
        this.$emit('quoteAdded', this.quote)
        this.quote = '';
      }
    }
  }
</script>

<style>
</style>
