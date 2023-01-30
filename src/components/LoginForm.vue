<template>
  <div>
    <h1>{{ title }}</h1>
    <form action="">
      <!-- username -->
      <label for="">User name</label>
      <input type="text" name="username" id="password" />
      <br />

      <!-- password -->
      <label for="">Password</label>
      <input type="text" name="password" id="password" />
      <br />
      <!-- Debug -->
      <span>Debug: {{ state.account }}</span>
      <!-- button -->
      <button>Submit</button>
      <button>Clear</button>
    </form>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted, reactive } from "vue";
export default defineComponent({
  props: ["title"],
  setup(props) {
    {
      const state = reactive({ account: { username: "", password: "" } });

      return {
        state,
      };
    }
  },
});
</script>
