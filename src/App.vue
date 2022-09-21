<template>
  <div class="layout-wrapper">
    <h2 class="title">ToDoList 예제 코드입니다.</h2>
    <to-do-write @register-to-do="registerToDo" />
    <to-do-list :todoItems="todoItems" />
  </div>
</template>

<script>
import ToDoList from "@/components/ToDoList";
import ToDoWrite from "@/components/ToDoWrite";

export default {
  name: 'App',
  components: {
    ToDoWrite,
    ToDoList,
  },
  data() {
    return {
      todoItems: []
    }
  },
  methods: {
    registerToDo(todoText) {
      console.log("registerToDo")
      //TODO:날짜 데이터 luxon 이용하기
      const data = new Date().toLocaleString().replace(/\./g, ".");
      const todo = {
        num:this.todoItems.length+1,
        content:todoText,
        addDate:data,
        updateDate:data,
        updateAt:'N',
        deleteAt:'N'
      }
      this.todoItems=[...this.todoItems,todo]
    }
  },
}
</script>

<style>
.layout-wrapper{
  text-align: center;
}
.title{
  margin: 50px 0;

}
</style>
