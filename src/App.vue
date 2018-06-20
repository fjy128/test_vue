<template>
  <div id="app">
    <!-- 头部 -->
    <header-a></header-a>
    <!-- 主体内容 -->
    <router-view/>
    <!-- 底部 -->
    <footer-a></footer-a>    
  </div>
</template>

<script>
import headerA from '../src/components/header';//头部
import footerA from '../src/components/footer';//底部
export default {
   components: {
        headerA,
        footerA
    },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}
</style>
