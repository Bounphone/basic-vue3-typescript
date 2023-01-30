<template>
  <div>
    <h1>App.vue</h1>
    <span>Count1: {{ count1 }}</span> <br />
    <span>Count2: {{ count2 }}</span> <br />
    <button @click="onClickAdd1">Add1</button>
    <button @click="onClickAdd2">Add2</button>
    <hr />
    <span>Account: {{ state.account }}</span>
    <button @click="onClickClearAccount">Clear</button>
    <hr>
    <LoginForm title="Login Form"/>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted, reactive, ref } from "vue";
import LoginForm from "@/components/LoginForm.vue";

const defaultAccount = { username: "", password: "" };

export default defineComponent({
  components: { LoginForm },
  setup() {
    let count1 = 100;
    const count2 = ref<number>(2);
    const state = reactive({
      account: { username: "admin", password: "123" },
    });

    onMounted(() => {
      // setInterval(onClickAdd2, 1000);
    });

    const onClickAdd1 = () => {
      count1 += count1;
    };

    const onClickAdd2 = () => {
      count2.value += count2.value;
    };

    const onClickClearAccount = () => {
      state.account = defaultAccount;
    };

    return {
      count1,
      count2,
      state,
      onClickAdd1,
      onClickAdd2,
      onClickClearAccount,
    };
  },
});
</script>
