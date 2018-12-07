<template>
  <div>
      <div class="border-bottom">
          <Tab v-on:toggle="ontoggle" v-bind:is-active="isActive" v-bind:items="items"></Tab>
          <div id="border" :style="{'width': 100/items.length+'%'}" class="nav-border bg-primary" ></div>
      </div>
      <gk-nav-content v-show="isActive==0">
          内容一
      </gk-nav-content>
      <gk-nav-content v-show="isActive==1">
          内容二
      </gk-nav-content>
      <gk-nav-content v-show="isActive==2">
          内容三
      </gk-nav-content>
  </div>
</template>

<script>
    import Tab from './components/gk-nav-tab'
    import GkNavContent from "@/components/gk-nav-tab-content";
    import $ from 'jquery'
    export default {
        name: 'App',
        components:{
            GkNavContent,
            Tab
        },
        data:function () {
            return {
                isActive:0,
                items:['未开始','进行中','已完成']
            }
        },
        methods:{
            ontoggle:function (index) {
                this.isActive = index;
                var leftLen = window.screen.width/(this.items.length)*index;
                $("#border").animate({left:leftLen},'fast');
            }
        }
    }
</script>

<style scoped>
@import "assets/css/bootstrap.css";
    .nav-border{
        position: relative;
        height: 3px;
    }
</style>
