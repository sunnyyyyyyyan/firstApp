<!--1.视图部分-->
<template>
  <div class="hello">
    {{hello}}
    {{1 + 1}}
    {{"哈哈"}}
    {{ 0 < 10 ? 'yes' : 'no'}}
    {{ 'attention:只能存在单行语句'}}
    <p>{{flag}}</p>
    <p v-html="sunny">july</p>
    <p v-text="sunny">may</p>
    <span v-bind:class="ha" >hahahaha</span>
    {{ message.split('').reverse().join('') }}
    <p v-if="show">can you see me</p>
    <div class="list">
      <ul>
        <li v-for="(name, index) in names" v-bind:key="index">{{name}}-{{index}}</li>
      </ul>
      <ul>
        <li v-for="(item,index) in user" :key="index">
          <span>{{item.name}}</span>
          <span>{{item.age}}</span>
        </li>
      </ul>
    </div>

    <button v-on:click="num += 1">按钮</button>
    <p>{{ num }}</p>
    <button v-on:click="handleClick()">按钮1</button>

  </div>
</template>

<!--2.逻辑部分-->
<script>
export default {
  name: 'HelloWorld',
  data(){
    return{
      num: 1,
      hello:'Hello, Vue',
      sunny:'sunny',
      "哈哈":"哈哈",
      flag:"我是flag",
      ha:'ha',
      message:'dare',
      show:true,
      names:['sunny','tom','lily'],
      user:[
        { id:0, name:'sunny',age:18},
        { id:1,name:'bill',age:28},
        { id:2,name:'anna',age:19}
      ]
    }

  },
  methods:{
    handleClick(){
      //alert("我是事件");
      console.log(this);  //this指向当前组件
      //this来索引当前data中的数据
      this.show = !this.show;
    }
  }
}
</script>

<!--3.样式部分-->
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.ha{
  background-color: red;
}

</style>
