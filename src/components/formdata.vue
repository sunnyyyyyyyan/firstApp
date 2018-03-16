<template>
    <div>
      <input type="text" v-model.trim="msg">
      <!--<p>{{msg}}</p>-->
      <p>{{message}}</p>
    </div>
</template>

<script>
    export default {
        name: "formdata",
      data(){
          return{
            msg:'hello',
            message:'hello'
          }
      },
      watch:{   //监听数据改变
          msg:function (data) {
            this.message = data;
            if( data == "haha"){
              console.log("hahhhhh");
            }


            /*  setTimeout(() => {        //网络请求延迟操作
                $.ajax({
                  url:'',
                  data:{
                    key:data
                  },
                  success:function (res) {
                    this.message = res;
                  }
                })

              },1000)
            */
          }
      }
    }
</script>

<style scoped>

</style>
