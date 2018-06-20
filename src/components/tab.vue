<template>
  <div id="dynamic-component-demo" class="demo">
  <button
    v-for="tab in tabs"
    v-bind:key="tab"
    v-bind:class="['tab-button', { active: currentTab === tab }]"
    v-on:click="currentTab = tab"
  >{{ tab }}</button>

  <component
    v-bind:is="currentTabComponent"
    class="tab"
  ></component>
<div>dasdas{{child}}{{age}}</div>
<button @click="getparent">传值给父亲</button>
</div>
</template>

<script>
export default {
  
    components: {
        'tab-home': {
            template: '<div>Home component</div>'
          },
        'tab-posts': {
            template: '<div>Posts component</div>' 
          },
        'tab-archive':{
            template: '<div>Archive component</div>'
          }
    },
    props:['child','age'],
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      currentTab: 'Home',
      tabs: ['Home', 'Posts', 'Archive'],
      parent:'给父亲的值哈哈哈'
    }
  },
   computed: {
    currentTabComponent: function () {
      return 'tab-' + this.currentTab.toLowerCase()
    }
  },
  methods:{
getparent(){
  console.log(this.parent)
  this.$emit('child-msg',this.parent);
}
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  scoped>
.tab-button {
  padding: 6px 10px;
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
  border: 1px solid #ccc;
  cursor: pointer;
  background: #f0f0f0;
  margin-bottom: -1px;
  margin-right: -1px;
}
.tab-button:hover {
  background: #e0e0e0;
}
.tab-button.active {
  background: #e0e0e0;
}
.tab {
  border: 1px solid #ccc;
  padding: 10px;
}
</style>


