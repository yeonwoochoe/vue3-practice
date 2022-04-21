<template>
  <button @click="message = 'good'">Click!</button>
  <h1>App: {{ message }}</h1>
  <Parent :msg="message" />
</template>

<script>
//부모자식간의 데이터 통신
import Parent from "~/components/Parent.vue";
import { computed } from "vue";

export default {
  components: {
    Parent,
  },
  data() {
    return {
      message: "Hello world",
    };
  },
  provide() {
    return {
      msg: computed(() => this.message),
    };
  },
};
</script>
