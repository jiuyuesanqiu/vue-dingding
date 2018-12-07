<template>
  <div>
    <div class="row">
      <bar-gird v-on:toggle="onToggle" :class="{'text-primary':isActive==index}" v-bind:index="index" class="col" v-for="(item,index) in items">{{item}}</bar-gird>
    </div>
  </div>
</template>

<script>
  import BarGird from './gk-nav-tab-item'
  export default {
    name: "gk-nav-bar",
    components:{
      BarGird
    },
    props:{
      items:{
        type:Array,
        required:true
      },
        isActive:Number
    },
      methods:{
        onToggle:function (index) {
            this.$emit("toggle",index);
        }
      }
  }
</script>

<style scoped>
  @import "../assets/css/bootstrap.css";
</style>
