<template>
    <div class="container">
      <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
      <app-new-quote @quoteAdded="newQuote"></app-new-quote>
      <p></p>
      <!-- <app-quote-grid :quotes="quotes"></app-quote-grid> -->
      <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
      <p></p>
      <div class="row">
          <div class="col-sm-12 text-center">
              <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
          </div>
      </div>
    </div>
</template>

<script>
  import QuoteGrid from './components/QuoteGrid.vue';
  import NewQuote from './components/NewQuote.vue';
  import Header from './components/Header.vue';
  export default {
    data: function() {
      return {
        quotes: [
          'Just a Sample quote'
        ],
        maxQuotes: 5
      }
    },
    methods: {
      newQuote(quote) {
        if (this.quotes.length >= this.maxQuotes) {
          return alert("Maximum Quote reached.")
        }
        this.quotes.push(quote)
      },
      deleteQuote(index) {
        this.quotes.splice(index, 1)
      }
    },
    components: {
      appQuoteGrid: QuoteGrid,
      appHeader: Header,
      appNewQuote: NewQuote
    }
  }
</script>

<style>
</style>
