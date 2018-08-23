<template>
  <div>
    <span
    @click="$emit('endTask', index)"
    id="task-span"
    :class="{ 'ended-task': todo.isEnded }">
        {{ todo.text | UpperCaseFilter }}
    </span>
    <span
    id="delete"
    @click="$emit('deleteTask', index)">&#8856;</span>
  </div>
</template>
<script>
import UpperCaseFilter from '../filters/uppercase';

export default {
  props: ['todo', 'index'],
  methods: {
  },
  filters: {
    UpperCaseFilter,
  },
};

</script>
<style>
</style>
