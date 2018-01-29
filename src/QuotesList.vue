<template>
  <div>
    <div class="wrapper">
      <div v-for="(quote, i) of quotes">
        <app-quote @click.native = "delete_quote(i)">
          <p>
            {{quote.text}}
          </p>
        </app-quote>
      </div>
    </div>
  </div>
</template>

<script>
  import AppQuote from './Quote.vue'
  import {EventBus} from './main.js'

  export default {
    name: "quotes-list",
    props: ['quotes'],
    data(){
      return {
      }
    },
    methods: {
      delete_quote(i){
        this.quotes.splice(i, 1)
      },
    },
    components: {
      AppQuote,
    },
    created(){
    },
  }
</script>

<style scoped>
  .wrapper {
    display: grid;
    grid-template-columns: repeat(4, 24%);
    grid-gap: 1%;
  }
</style>
