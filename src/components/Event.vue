<template>
    <!-- 在template中，只能存在一个根组件  -->
    <div class="event">
      <ul>
        <li v-on:click.once="getItemInfo(index,$event)" v-for="(name,index) in names">{{name}}</li>
      </ul>
      <input type="text" v-on:keyup.enter="getKeyInfo($event)">
      <button v-on:click="pushArr()">按钮</button>
      <button v-on:click="getOdd()">我要奇数</button>
      <div>
        <p>{{msgRe}}</p>
        <p>{{msgRe}}</p>
      </div>

    </div>
</template>

<script>
    export default {
      //data中的数据改变，会引起视图的改变 MVVM
        data(){
          return{
            names:['sunny','bill','sky'],
            nums:[1,2,3,4,5,6,7,],
            message:'sunny'
          }
        },
      methods:{
        //事件中的默认参数event
        getItemInfo(data,event){
          console.log(this.names[data]);
          console.log(event);
        },
        getKeyInfo(event){
          console.log(event);
        },
        pushArr(){
          //this.names.push('tom');
          this.names.concat(["frank"]);
        },
        getOdd(){
          this.nums.filter(function (num) {
            if(num % 2 !== 0){
              console.log(num);
            }
            //console.log(num % 2 !== 0);
            return num % 2 !== 0;
          })
        }
      },
      computed:{   //计算属性
        msgRe(){
          return this.message.split('').reverse().join('');
        }
      }
    }
</script>

<style scoped>

</style>
