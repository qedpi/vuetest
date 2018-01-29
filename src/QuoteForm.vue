<template>
  <div>
    <div id="quote_form">
      <p>Quote</p>
      <textarea v-model = "quote_text" cols="60" rows="5"></textarea>
      <br><br>
      <button @click = "add_quote" class="btn btn-primary">Add Quote</button>
    </div>
  </div>
</template>

<script>
  import {EventBus} from './main.js'

  export default {
    name: "quote-form",
    data(){
      return {
        quote_text: '',
      }
    },
    methods: {
      add_quote(){
        this.$emit('add_quote', this.quote_text)
        this.quote_text = ''
      }
    },
  }
</script>

<style scoped>
  #quote_form {
    text-align: center;
  }
  input {
    height: 5em;
    width: 50%;
  }
</style>
