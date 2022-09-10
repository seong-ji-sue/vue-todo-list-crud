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
      todoItems: [
        {num:1, content:"이상한 변호사 우영우 보기",addDate:"2012-02-02",updateDate:"2012-02-02",updateAt:'N',deleteAt:'N'},
      ]
    }
  },
  methods: {
    registerToDo(todoText) {
      //TODO:날짜 데이터 luxon 이용하기
      const data = new Date().toLocaleDateString().replace(/\./g, ".");
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
