<template>
  <div class="wrapper">

    <table class="table common-table-border">
      <thead>
        <tr>
          <th v-for="(headers,index) in headerData"
              :key="`header-${index}`"
              class="common-cell-padding common-table-border">
            {{headers.text}}
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(todo,index) in todoItems" :key="`todo-row-${index}`">
          <td v-for="(headers,index) in headerData"
              :key="`todo-cell-${index}`"
              class="common-cell-padding common-table-border">
            <button v-if="headers.name ==='updateAt'">수정</button>
            <button v-else-if="headers.name==='deleteAt'">삭제</button>
            <slot v-else>
              {{todo[headers.name]}}
            </slot>
          </td>
        </tr>
      </tbody>
    </table>
  </div>

</template>

<script>/**
 * 미션~!!
 * 1. Vuetify를 활용해서 레이아웃을 그린다.
 * 2. input 박스에 텍스트를 입력시 리스트 배열에 추가 한다.
 * 3. Delete 버튼을 클릭하면 리스트에서 사라진다
 * 4. Update 버튼을 클릭시 텍스트가 input 박스로 바뀌고 수정할 수 있다.
 * 5. 방향키를 누르면 순서를 바꿀 수 있다.
 * 6. Vuex로 해당 메소드 변수를 전역에서 관리한다.
 */
import headerData from "@/data/headerData";

const header = headerData

export default {
  name: "ToDoList",
  data() {
    return {
    headerData: header.toDoHeaderData
    }
  },
  props: {
    todoItems: {
      type: Array,
      default: ()=>[]
    },
  },

}
</script>

<style scoped>
.common-table-border{
  border: 1px solid black;
}
.common-cell-padding{
  padding: 10px;
}
.wrapper{
  display: flex;
  flex-direction: column;
  align-items: center;
}

.table{
  margin: 50px;
  width: 80%;
  border-spacing: 0px;
}

</style>