<template>
  <div>
    <div class="container">
      <app-progress-bar :num_quotes="quotes.length" :limit = "max_quotes"></app-progress-bar>
      <app-quote-form @add_quote = "add_quote"></app-quote-form>
      <br><br>
      <div class="container">
        <app-quotes-list :quotes = "quotes"></app-quotes-list>
      </div>
      <br><br>
      <app-footer></app-footer>
    </div>
  </div>
</template>

<script>
  import AppProgressBar from './ProgressBar.vue'
  import AppQuoteForm from './QuoteForm.vue'
  import AppQuotesList from './QuotesList.vue'
  import AppFooter from './AppFooter.vue'

  export default {
    components: {
      AppProgressBar,
      AppQuoteForm,
      AppQuotesList,
      AppFooter,
    },
    data() {
      return {
        quotes: [],
        max_quotes: 5,
      }
    },
    methods: {
      add_quote(quote){
        if (this.quotes.length < this.max_quotes){
          this.quotes.push({text: quote})
        } else {
          alert('Max number of quotes (' + this.max_quotes + ') already reached!')
        }
      },
    },
  }
</script>

<style lang="scss">

</style>
