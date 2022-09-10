<template>
  <div class="wrapper">
    <h2 class="title">ToDoList 예제 코드입니다.</h2>
    <input
        placeholder="오늘 해야 될 일 적기"
        type="text"
        class="write-todo-input"
        v-model="todoText"
    />
    <table class="table common-table-border">
      <thead>
        <tr>
          <th class="common-cell-padding common-table-border">순서</th>
          <th class="common-cell-padding common-table-border">내용</th>
          <th class="common-cell-padding common-table-border">추가날짜</th>
          <th class="common-cell-padding common-table-border">수정날짜</th>
          <th class="common-cell-padding common-table-border">수정하기</th>
          <th class="common-cell-padding common-table-border">삭제하기</th>

        </tr>
      </thead>
      <tbody>
        <tr>
          <td class="common-cell-padding common-table-border">1</td>
          <td class="common-cell-padding common-table-border">아이스크림 먹기</td>
          <td class="common-cell-padding common-table-border">추가날짜</td>
          <td class="common-cell-padding common-table-border">수정날짜</td>
          <td class="common-cell-padding common-table-border">수정하기</td>
          <td class="common-cell-padding common-table-border">삭제하기</td>
        </tr>
      </tbody>
    </table>
  </div>

</template>

<script>
/**
 * 미션~!!
 * 1. Vuetify를 활용해서 레이아웃을 그린다.
 * 2. input 박스에 텍스트를 입력시 리스트 배열에 추가 한다.
 * 3. Delete 버튼을 클릭하면 리스트에서 사라진다
 * 4. Update 버튼을 클릭시 텍스트가 input 박스로 바뀌고 수정할 수 있다.
 * 5. 방향키를 누르면 순서를 바꿀 수 있다.
 * 6. Vuex로 해당 메소드 변수를 전역에서 관리한다.
 */
export default {
  name: "ToDoList",
  data() {
    return {
      todoText: ''
    }
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
.title{
  margin: 50px 0;

}
.write-todo-input {
  border: 2px solid black;
  border-radius: 3px;
  padding: 10px;
  width: 60%;
}
.table{
  margin: 50px;
  width: 60%;
  border-spacing: 0px;
}

</style>