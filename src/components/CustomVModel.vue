<template>
  <div>
    <h1>Custom V-Model</h1>
    <input type="text" name="message" id="message" :value="message" @change="onChange"/>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: ["message"],
  emits:["update:message"],
  setup(props, {emit}) {
      const onChange = (event:any)=>{
        emit("update:message", event.target.value)          
      }
    return {onChange};
  },
});
</script>
