<template>
  <div class="text-ceter">
    <h2 class="text-center">
      Counter
    </h2>
    <p>{{ state.message }}</p>
    <button
      class="bg-green-700 text-white rounded px-4 py-1 focus:shadow-md focus:outline-none"
      @click="add"
    >
      +</button><span class="p-4">{{ state.counter }}</span><button
      class="bg-red-600 text-white rounded px-4 py-1 focus:shadow-md focus:outline-none"
      @click="remove"
    >
      -
    </button>
    <input
      id="view"
      type="checkbox"
      name="view"
      @change="visible"
    > Do you parchage this product using creadit?
    <div v-if="state.isVisible">
      <div>
        <input
          id="showMonth"
          type="checkbox"
          name="threeMonths"
        > 3 Months
        <input
          id="showMonth"
          type="checkbox"
          name="sixMonths"
        > 6 Months
        <input
          id="showMonth"
          type="checkbox"
          name="oneYear"
        > 12 Months
        <li
          v-for="monthlist in state.months"
          :key="monthlist"
        >
          <p>{{ monthlist }}</p>
        </li>
      </div>
    </div>
  </div>
</template>

<script>
import { reactive, watch, computed } from 'vue';
export default {
  setup(props) {
    const state = reactive({
      message: 'Hello World',
      counter: 1,
      isVisible: false,
      isMonth: false,
      months: 1,
    });

    const reverseMessage = () => {
      state.message = state.message.split('').reverse().join('');
    };

    const add = () => {
      state.counter++;
    };

    const visible = () => {
      state.isVisible = !state.isVisible;
    };

    const addMonth = () => {
      let numOfMonth = document.getElementById('showMonth').value;
      state.counter = numOfMonth;
    };

    const remove = () => {
      state.counter--;
    };

    return {
      addMonth,
      visible,
      state,
      reverseMessage,
      add,
      remove,
    };
  },
};
</script>
