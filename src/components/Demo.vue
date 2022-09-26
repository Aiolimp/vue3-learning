<template>
  <!--vue3的组件模版结构可以没有根标签-->
  <span>{{sum}}</span>
  <button @click="sum++">总数+1</button>
  <br>
  <span>{{msg}}</span>
  <button @click="msg+='!'">点击msg</button>
  <br>
  <span>姓名:{{person.name}}</span>
  <br>
  <span>年龄:{{person.age}}</span>
  <br>
  <span>薪水:{{person.job.j1.slaly}}</span>
  <br>
  <button @click="person.name+='~'">点击姓名</button>
  <button @click="person.age++">点击年龄</button>
  <button @click="person.job.j1.slaly++">点击薪水</button>
</template>

<script>
import { ref,watch,reactive } from 'vue';
export default {
  name: 'Demo',
  setup(){
    let sum = ref(0)
    let msg = ref('你好啊')
    let person = reactive({
      name:'张三',
      age:'24',
      job:{
        j1:{
          slaly:20
        }
      }
    })
    watch(()=>person.job,(newVal,oldVal)=>{
      console.log(newVal,oldVal)
    })
    //返回一个对象
    return {
      sum,
      msg,
      person
    }
  }
}
</script>

<style>
</style>
