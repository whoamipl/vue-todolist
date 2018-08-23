<template>
  <div id="app">
    <input type="text" id="input" placeholder="Co chcesz dzisiaj zrobić?" @keyup="addTodo($event)">
    <TodoList :todos="tasks"/>
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue';

export default {
  name: 'app',
  data() {
    return {
      tasks: [{
        text: 'Zadanie 1',
        isEnded: false,
      },
      {
        text: 'Zadanie 2',
        isEnded: false,
      },
      {
        text: 'Zadanie 3',
        isEnded: true,
      }],
    };
  },
  methods: {
    addTodo(event) {
      if (event.target.value === '') { return; }
      if (event.which === 13) {
        this.tasks.push({
          text: event.target.value,
          isEnded: false,
        });
        event.target.value = '';
      }
    },
  },
  components: {
    TodoList,
  },
};
</script>

<style>
* {
    box-sizing: border-box;
}
html {
    background: linear-gradient(to bottom, #000, #434343);
    background-attachment: fixed;
    color: #fff;
    font-family: "Lucida Console", Monaco, monospace;
}
ul {
    list-style: none;
    width: 694;
}
#task {
    padding: 5px;
    font-size: 16pt;

}
.ended-task {
    color: gray;
    text-decoration: line-through;
}
input {
    text-align: center;
    background-color: inherit;
    border: 0;
    font-size: 36pt;
}

input:focus {
    outline: none;
    opacity: 0;
}

#app {
    min-width: 100%;
    min-height: 400px;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}

#selector {
    flex-direction: row;
}

a {
    text-decoration: none;
    color: black;
}

#task-span {
    float: left;
    width: 300px;
    cursor: pointer;
}

#delete {
    cursor: pointer;
}
</style>
