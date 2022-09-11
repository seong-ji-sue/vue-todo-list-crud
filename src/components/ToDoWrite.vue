<template>
  <div class="wrapper">
    <div class="input-wrapper">
      <input
          :placeholder="showPlaceholderText"
          type="text"
          class="write-todo-input"
          :value="todoText"
          @input="onInput"
          @keyup.enter="onRegister"
      />
      <span v-if="error" class="error-style">{{error}}</span>
    </div>
    <button class="add-button" @click="onRegister">할일 추가</button>
  </div>
</template>

<script>
export default {
  name: "ToDoWrite",
  data() {
    return {
      todoText: '',
      placeholder:"오늘 해야 될 일 적기",
      error:''
    }
  },
  computed: {
    showPlaceholderText(){
      return !this.todoText ? this.placeholder : ''
    }
  },
  methods: {
    onInput(e){
      const value=e.target.value;
      if (!value) {
        this.error = '해야 될 일을 적어주세요.';
      }else{
        this.error = ''
      }
      this.todoText=value
    },
    onRegister() {
      this.$emit("register-to-do",this.todoText)
      this.todoText=''
    },
  },
}
</script>

<style scoped>
.wrapper{
  display: flex;
  justify-content: center;
}
.input-wrapper{
  display: flex;
  flex-direction: column;
  width: 50%;
}
.write-todo-input {
  border: 2px solid black;
  border-radius: 3px;
  padding: 10px;
  margin-right: 10px;
}
.add-button{
  border: 2px solid black;
  border-radius: 3px;
  padding: 10px;
  cursor: pointer;
  background-color: aqua;
  height: 80%;
}
.error-style{
  text-align: left;
  margin-left: 12px;
  color : #ff5252 !important;
  font-size: 13px;
}
</style>