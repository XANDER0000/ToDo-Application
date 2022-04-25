<template>
<div class="search__wrapper">
 <input @keyup.enter ="makeNewTodo(todoValue)" v-model="todoValue" autofocus class="search__input" placeholder="Name of the Task" type="text">
 <button @click="makeNewTodo(todoValue)" class="btn">Add new ToDo</button>
</div>

</template>

<script>
export default {
 name: 'MainSearch',

 data: () => ({
  todoValue: '',
 }),

 methods: {
    makeNewTodo(todoValue) {
     this.$emit('makeNewTodo', todoValue);
     this.todoValue =  '';
   },
  }
}
</script>

<style lang="less" scoped>
.search__wrapper {
 display: flex;
 justify-content: center;
 margin-top: 30px;
}

.search__input {
 border: 0;
 border-radius: 2px;
 margin-right: 7px;
 padding: 0 0 0 10px;
 font-size: 17px;
 letter-spacing: .6px;
 outline: none;
 width: 500px;
 background: #e1e1e1;

 &:focus {
  border: 1.5px solid #5fc9c9;
  -webkit-box-shadow: 0px 0px 11px 4px rgba(95, 201, 201, 0.23);
  -moz-box-shadow: 0px 0px 11px 4px rgba(95, 201, 201, 0.23);
  box-shadow: 0px 0px 11px 4px rgba(95, 201, 201, 0.23);
 }
}
</style>