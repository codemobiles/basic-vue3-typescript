<template>
  <div>
    <h1>{{ title }}</h1>
  </div>
</template>
<script lang="ts">
import { defineComponent, onMounted } from "vue";

export default defineComponent({
  props: ["title"],
  setup(props) {
    {
      onMounted(() => {
          console.log("props: " +  props.title)
      });

      return {};
    }
  },
});
</script>
