<template>
  <div id="quotebox">
    <div class="card card-primary">
      <slot></slot>
    </div>
  </div>
</template>

<script>
  export default {
    name: "quote",
  }
</script>

<style scoped>
  #quotebox {
    text-align: center;
    cursor: pointer;

  }

  .card:hover {
    background-color: lightcoral;
  }
</style>
