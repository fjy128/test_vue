<template>
  <div class="hello">
    <h1>Community</h1>
    
  <!-- <tab></tab> -->
  </div>
</template>

<script>
export default {//
     data(){
        return{
       res:[],
        }
    },
    mounted(){
      this.getData()
    },
    methods:{
      getData(){ 
        $.ajax({
            url: "http://5b076a5892b3b4001425a067.mockapi.io/api/banner/question",
            type: 'get',
            dataType: 'json',
            data: {},
            success:res=>{ console.log(res) ;this.res=res },
            error:msg=>{ console.log(msg)}
        })      
     }   
    }
}
</script>
<style scoped>

</style>
