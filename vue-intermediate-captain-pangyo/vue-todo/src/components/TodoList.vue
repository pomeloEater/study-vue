<template>
  <div>
    <transition-group name="list" tag="ul">
      <li v-for="(todoItem, index) in storedTodoItems" v-bind:key="index" class="shadow">
        <i class="fa-solid fa-check checkBtn" 
          v-bind:class="{checkBtnCompleted: todoItem.completed}"
          v-on:click="toggleComplete({todoItem, index})"></i>
        <span v-bind:class="{textCompleted: todoItem.completed}">
          {{todoItem.item}}
        </span>
        <span class="removeBtn" v-on:click="removeTodo({todoItem, index})">
          <i class="fa-solid fa-trash-can"></i>
        </span>
      </li>
    </transition-group>
  </div>
</template>

<script>
import {mapGetters, mapMutations } from 'vuex';

export default {
  methods: {
    ...mapMutations({
      removeTodo: 'removeOneItem',
      toggleComplete: 'toggleOneItem'
    })
  },
  computed: {
    ...mapGetters(['storedTodoItems'])
    /* 
      <li v-for="(todoItem, index) in todoItems"
      와 같이 컴포넌트에 사용되는 메서드 명과 store의 메서도 명이 다른 경우에는
      ...mapGetters({
        todoItems: 'storedTodoItems'
      })
      와 같이 JSON으로 쓸 수 있다
    */
  }
}
</script>

<style scoped>
ul {
  list-style-type: none;
  padding-left: 0px;
  margin-top: 0;
  text-align: left;
}
li {
  display: flex;
  min-height: 50px;
  height: 50px;
  line-height: 50px;
  margin: 0.5rem 0;
  padding: 0 0.9rem;
  background: white;
  border-radius: 5px;
}
.checkBtn {
  line-height: 45px;
  color: #52acde;
  margin-right: 5px;
}
.checkBtnCompleted {
  color: #b3adad;
}
.textCompleted {
  text-decoration: line-through;
  color: #b3adad
}
.removeBtn {
  margin-left: auto;
  color: #de4343;
}

.list-enter-active, .list-leave-active {
  transition: all 1s;
}
.list-enter, .list-leave-to /* .list-leave-active below version 2.1.8 */ {
  opacity: 0;
  transform: translateY(30px);
}
</style>