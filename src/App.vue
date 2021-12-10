<template>
  <div>
    <h1>App.Vue</h1>
    <span>#Count1: {{ count1 }}</span> <br>
    <span>#Count2: {{ count2 }}</span> <br>
    <button @click="onClickAdd1">Add1</button>
    <button @click="onClickAdd2">Add2</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({    
  setup() {
    let count1 = 1;
    const count2 = ref<number>(2)

    const onClickAdd1 = ()=>{
        count1 = count1 + 1
        console.log("count1 = " + count1)
    }

    const onClickAdd2 = ()=>{
        count2.value = count2.value + 1
        console.log("count1 = " + count2.value)
    }

    return {
      count1,
      count2,
      onClickAdd1,
      onClickAdd2,
    };
  },
});
</script>
