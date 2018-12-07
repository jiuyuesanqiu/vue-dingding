<template>
  <div>
    <div class="d-flex p-3 justify-content-center" v-on:click="$emit('toggle',index)">
      <span>
        <slot></slot>
      </span>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'App',
    props:{
      index:Number
    }
  }
</script>

<style scoped>
  @import "../assets/css/bootstrap.css";

</style>
