<!--复习梳理计算属性的用法-->
<template>
  <div class="container">
     <h1>{{title}}</h1>
    <button @click="setNewName('z', 'yy')">修改姓名为zyy</button>
    <button @click="setNewName()">还原姓名</button>
    <hr/>
      <p> 姓: {{firstName}}</p>
      <p> 名：{{lastName}}</p>
      <h2>===使用方法来计算全名===</h2>
      <p> 全名: {{getFullName()}}</p>
      <p> 全名: {{getFullName()}}</p>
      <p> 全名: {{getFullName()}}</p>
      <p> 全名: {{getFullName()}}</p>
     <h2>===使用计算属性来计算全名===</h2>
      <p> 全名: {{getFullNameByComputed}}</p>
      <p> 全名: {{getFullNameByComputed}}</p>
      <p> 全名: {{getFullNameByComputed}}</p>
      <p> 全名: {{getFullNameByComputed}}</p>
    <h2>===使用计算属性完整写法来计算全名===</h2>
    <p> 全名: {{getFullNameByComputedWZ}}</p>
    <button @click="getFullNameByComputedWZ='完整'"> 计算属性完整写法修改姓名为完整</button>

  </div>
</template>

<script >
    export default {
      data(){
        return {
          title: '计算属性用法梳理',
          firstName: '左',
          lastName: '永义'
        }
      },
      //使用方法来计算全名
      methods: {
        getFullName(){
          console.log("method:使用方法来计算全名");
          return this.firstName + ' ' + this.lastName;
        },


        setNewName(firstName='左', lastName='永义'){  //重新设置姓 + 名
          this.firstName = firstName;
          this.lastName=lastName;
        },
      },

      //使用计算属性来得到全名
      computed: {
        getFullNameByComputed(){
          console.log("computed:使用计算属性来计算全名");
          return this.firstName + ' ' + this.lastName;
        },

        getFullNameByComputedWZ:{ //计算属性完整写法
          get(){  //得到
            return this.firstName + ' ' + this.lastName;
          },
          set(newFullName){  //修改
            this.firstName=newFullName[0];
            this.lastName=newFullName[1];
          }
        },
      }

    }
</script>
<style >
  p {
    font-size: 20px;
  }
</style>