<template>

  <div>
    <!--<p v-bind:class="{active:isActive, 'demo':Demo}">hhhha</p>-->
    <p v-bind:class="styleObj">hhhha</p>
    <p v-bind:class="[demo1, demo2]">hhhha</p>
    <p v-bind:class="[{active:isActive},'info-'+id]">hhhha</p>
    <ul>
      <li :class="[{active:index%2 == 0},'info-'+id]" v-for="(name,index) in names">{{name}}</li>
    </ul>
    <div>
      <p :style="stob">hhhhhha</p>
    </div>

  </div>
</template>

<script>
    export default {
        name: "",
      data(){
          return{
            /*isActive:false,
            Demo:true*/

            /*styleObj:{
              active:true,
              'demo':false
            }*/

            id:10,
            isActive:true,
            isDemo:true,
            demo1:'demo11',
            demo2:'demo22',
            names:['sunny','tom','bill','lily'],
            stob:{
              color:'red',
              fontSize:'30px'
            }
          }
      },
      computed:{
        styleObj(){
          return{
            'active':this.isActive,
            'demo':this.isDemo
          }
        }
      }
    }
</script>

<style scoped>

  .active{
    /*color:red;*/
    background: #f1f1f1;
  }
</style>
