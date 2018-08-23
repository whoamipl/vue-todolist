<template>
  <div id="container">
        <div>
            <ul v-if="todos">
                <li id="task" v-for="(todo, index) in todos" :key="index">
                    <todo-element
                    :todo="todo"
                    :index="index"
                    @endTask="endTask"
                    @deleteTask="deleteTask"
                    />
                </li>
            </ul>
        </div>
    </div>
</template>
<script>
import TodoElement from './TodoElement.vue';


export default {
  name: 'TodoList',
  props: ['todos'],
  components: {
    TodoElement,
  },
  methods: {
    deleteTask(index) {
      this.todos.splice(index, 1);
    },
    endTask(index) {
      this.todos[index].isEnded = true;
    },
  },
};
</script>
<style>

</style>

