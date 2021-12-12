<template>
  <div>
    <h1>App.Vue</h1>
    <span>#Count1: {{ count1 }}</span> <br />
    <span>#Count2: {{ count2 }}</span> <br />
    <button @click="onClickAdd1">Add1</button>
    <button @click="onClickAdd2">Add2</button>
    <hr />
    <span>#Account: {{ states.account }}</span> <br />
    <button @click="onClickClearAccount">Clear</button>
    <hr>
    <!-- reorder ep10 -->
    <LoginForm title="Login" @submitLogin="onSubmitLogin"/>    
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, reactive, onMounted } from "vue";
import LoginForm from "@/components/LoginForm.vue";

const defaultAccount = { username: "", password: "" };

export default defineComponent({
  components: {
    LoginForm,
  },
  setup() {
    let count1 = 1;
    const count2 = ref<number>(2);
    const states = reactive({
      account: { username: "admin", password: "1234" },
    });

    // https://v3.vuejs.org/guide/composition-api-lifecycle-hooks.html
    onMounted(() => {
      setInterval(onClickAdd2, 1000);
    });

    const onClickAdd1 = () => {
      count1 = count1 + 1;
      console.log("count1 = " + count1);
    };

    const onClickAdd2 = () => {
      count2.value = count2.value + 1;
      console.log("count1 = " + count2.value);
    };

    const onClickClearAccount = () => {
      // account.username = ""
      // account.password = ""
      states.account = defaultAccount;
    };

    const onSubmitLogin  = ()=>{
      alert("1234")
    }

    return {
      count1,
      count2,
      onClickAdd1,
      onClickAdd2,
      states,
      onClickClearAccount,
      onSubmitLogin
    };
  },
});
</script>
