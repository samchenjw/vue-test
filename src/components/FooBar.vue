<template>
  <div>
     <div class="hello">{{ message }} --- {{ data }}---{{ bmi }}</div>
     <button v-on:click="add()">submit</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, computed, reactive, } from "vue";

export default defineComponent({
  props: {
    message: String,
  },
  setup(props) {
    const state = reactive({
      height: 180,
      weight: 80,
    });
    let data: number = 10;
    console.log(props.message);
    const bmi = computed(() => {
      console.log('run111')
      return state.weight / Math.pow(state.height / 100, 2);
    });

    return {
      data,
      bmi,
      add(){
        state.height++;
      }
    };
  },
});
</script>
