<template>
  <div>
    <h1>Quotes Added</h1>
    <div>
      <div class="progress-bar" :style="{width: 100 * (num_quotes / limit) + '%'}">
        <p>{{num_quotes}} / {{limit}}</p>
      </div>
    </div>
  </div>
</template>

<script>
  import {EventBus} from './main.js'

  export default {
    name: "progress-bar",
    props: {
      'num_quotes': Number,
      'limit': Number,
    },
  }
</script>

<style scoped>
  #barouter {
    background-color: lightgray;
    width: 100%;
    height: 20px;
    border: 1px solid darkgray;
    margin: 3em;
  }

  #barinner {
    background-color: blue;
    height: 100%;
    color: white;
    text-align: center;
    transition: width 500ms;
  }
</style>
