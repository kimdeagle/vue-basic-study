<template>
  <div id="app">
    <!-- {{ message }} -->
    <!-- <span v-bind:title="message">마우스 올리면 title이 출력됩니다.</span> -->
    <!-- <p v-if="seen">보인다</p> -->
    <!-- <ol>
      <li v-for="todo in todos" :key="todo">{{ todo.text }}</li>
    </ol> -->
    <p>{{ message }}</p>
    <!-- <button v-on:click="reverseMessage">메시지 뒤집기</button> -->
    <input type="text" v-model="message">
    <ol>
      <li v-for="(item, index) in todos" :key="index">
        <todo :label="item.text" :done="true"></todo>
      </li>
    </ol>
  </div>
</template>

<script>
import Todo from "./components/Todo.vue";

export default {
  name: 'App',
  components: {
    Todo
  },
  data() {
    return {
      message: "hello!",
      seen: true,
      todos: [
        { text: "Vue.js 공부" },
        { text: "Spring Security 공부" },
        { text: "모름" },
      ]
    }
  },
  methods: {
    reverseMessage() {
      this.message = this.message.split('').reverse().join('')
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
