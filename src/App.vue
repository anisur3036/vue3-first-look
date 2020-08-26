<template>
  <Counter />
</template>

<script>
import Todo from './components/Todo.vue';
import Another from './components/Another.vue';
import Counter from './components/Counter.vue';

export default {
  name: 'App',
  components: {
    Todo,
    Another,
    Counter
  },
};
</script>
