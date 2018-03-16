<template>
    <div>
        父组件
      <input type="text" v-model="num">
      <Child @sendmsg="getMsg" :num = "getNum"></Child>
      {{info}}
    </div>
</template>

<script>

  import Child from './child'
    export default {
      name: "parent",
      data(){
        return{
          info:'',
          num:1
        }
      },
      computed:{
        getNum(){         //类型转换，页面input的类型是String
          return this.num - 0;
        }
      },
      components:{
          Child
      },
      methods:{
        getMsg(data){
          //console.log(data);
          this.info = data;
        }
      }
    }
</script>

<style scoped>

</style>
