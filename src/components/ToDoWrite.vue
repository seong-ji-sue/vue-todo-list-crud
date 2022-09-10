<template>
  <div>
    <input
        placeholder="오늘 해야 될 일 적기"
        type="text"
        class="write-todo-input"
        v-model="todoText"
    />
    <button class="add-button" @click="onRegister">할일 추가</button>
  </div>
</template>

<script>
export default {
  name: "ToDoWrite",
  data() {
    return {
      todoText: ''
    }
  },
  methods: {
    onRegister() {
      this.$emit("register-to-do",this.todoText)
      this.todoText=''
    }
  },
}
</script>

<style scoped>
.write-todo-input {
  border: 2px solid black;
  border-radius: 3px;
  padding: 10px;
  width: 50%;
  margin-right: 10px;
}
.add-button{
  border: 2px solid black;
  border-radius: 3px;
  padding: 10px;
  cursor: pointer;
  width: 10%;
  background-color: aqua;
}
</style>