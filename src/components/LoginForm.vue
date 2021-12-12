<template>
  <div>
    <h1>{{ title }}</h1>
    <form>
      <!-- username -->
      <label for="username">Username: </label>
      <input type="text" name="username" id="username" v-model="states.account.username" />
      <br />
      <!-- password -->
      <label for="password">Password: </label>
      <input type="text" name="password" id="password" v-model="states.account.password"/>
      <br />
      <!-- buttons -->
      <button type="button" @click="onClickLogin">Submit</button>
      <button type="button" @click="onClickClear">Clear</button>
      <br>
      <span>#Debug: {{states.account}}</span>
    </form>
  </div>
</template>
<script lang="ts">
import { defineComponent, onMounted, reactive } from "vue";

export default defineComponent({
  emits: ["submitLogin"],
  props: ["title"],
  setup(props, {emit}) {
    {
      const states = reactive({account: {username:"", password:"" }})

      const onClickClear = ()=>{
          states.account = {username:"", password:"" }
      }

      const onClickLogin = ()=>{
        emit("submitLogin")
      }


      return {states, onClickClear, onClickLogin};
    }
  },
});
</script>
