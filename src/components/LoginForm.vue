<template>
  <div>
    <h1>{{ title }}</h1>
    <form>
      <!-- username -->
      <label for="username">Username: </label>
      <input type="text" name="username" id="username" />
      <br />
      <!-- password -->
      <label for="password">Password: </label>
      <input type="text" name="password" id="password" />
      <br />
      <!-- buttons -->
      <button>Submit</button>
      <button>Clear</button>
      <br>
      <span>#Debug: {{states.account}}</span>
    </form>
  </div>
</template>
<script lang="ts">
import { defineComponent, onMounted, reactive } from "vue";

export default defineComponent({
  props: ["title"],
  setup(props) {
    {
      const states = reactive({account: {username:"", password:"" }})

      return {states};
    }
  },
});
</script>
