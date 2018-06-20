<template>
  <div class="hello">
    <h1 :title="moveshow" v-if="isshow">{{msg}}</h1>
    <h2 v-else>2222</h2>
    <div :class="{ red: isRed }">{{changeval}}</div>
    <div :class="['classA', 'classB']">adasdas</div>
    <div :class="['classB', {  red: isRed  }]">eeeee</div>
     <div  :style="{ fontSize: size + 'px' } " @click="changeBig">变大</div>
     <div :style="[styleObjectA, styleObjectB]">fsfsf</div>
    <button @click="fnChange">改变值</button>
    <div>
      <input v-model="message" placeholder="edit me">
      <p>Message is: {{ message }}</p>
    </div>
    <br>
    <div id='example-3'>
      <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
      <label for="jack">Jack</label>
      <input type="checkbox" id="john" value="John" v-model="checkedNames">
      <label for="john">John</label>
      <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
      <label for="mike">Mike</label>
      <br>
      <span>Checked names: {{ checkedNames }}</span>
    </div>
<div v-cloak>
  {{ message }}
</div>
<p><input  v-model="msg"/></p>
<span v-once>This will never change: {{msg}}</span>
    <ul>
      <li v-for="(item,index) in items" :key="index" @click="doThis(item.name)">{{item.name}}</li>
    </ul>


    <!-- 子组件 -->
  <tab-a :child='getchild' :age="age" v-on:child-msg="getChildData"></tab-a>
  <div>父组件：{{childMsg}}</div>
  </div>
</template>

<script>
import tabA from '@/components/tab'
export default {
  name: 'HelloWorld',
  components:{
    tabA
  },
  data () {
    return {
      getchild:'吃饭了',
      childMsg:'',
      age:18,
      isRed:true,
      isshow:true,
      changeval:'moren',
      size:12,
      message:'输入吧',
      checkedNames: [],
      moveshow:'鼠标移上显示',
      msg: 'Welcome to Your Vue.js App',
      items:[
        {name:'苹果'},
        {name:'香蕉'},
        {name:'香梨'}
      ],

  styleObjectA:{
    'color':'pink'
  },
  styleObjectB:{
    'fontSize':'20px'
  }
    }
  },
  methods:{
    doThis:function(item){
      alert(item)
    },
    fnChange(){
      this.changeval='改变值'
    },
    changeBig(){
      this.size++
    },
    getChildData(msg){
        this.childMsg=msg;
    }
  }
}
</script>

<style scoped>
.red{
  color:red
}
.classA{
    color:green
    }
.classB{
  font-size:24px
}
</style>
