<template>
  <div>
    子组件
    <button @click="sendMsg">传递</button>
  </div>
</template>

<script>
    export default {
        name: "child",
        data(){
          return{
              msg:'I am child'
          }
        },
      props:{
        num:{
          type:Number,
          default:5
        }
      },
      computed:{
        addNum(){
          return this.num * 5;
        }
      },
      methods:{
          sendMsg(event){
            //两个参数：参数1：key   参数2：数据
            this.$emit('sendmsg',this.addNum)   //子 传递数据给父
          }
      }
    }
</script>

<style scoped>

</style>
