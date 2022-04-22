<template>
  <h1 @click="increase">{{ count }} / {{ doubleCount }}</h1>
  <h1 @click="changedMessage">{{ message }} / {{ reversedMessage }}</h1>
</template>
<script>
import { ref, computed, watch, onMounted } from "vue";

export default {
  setup() {
    //setup은 created 라이프싸이클 훅과 동일한 동작을하기 떄문에
    //컴포지션 api 내부에  별도의 created 함수가 없다
    const count = ref(0);
    const doubleCount = computed(() => {
      return count.value * 2;
    });
    function increase() {
      count.value += 1;
    }

    const message = ref("Hello World");
    // eslint-disable-next-line vue/no-side-effects-in-computed-properties
    const reversedMessage = computed(() =>
      message.value.split("").reverse().join("")
    );
    // eslint-disable-next-line prettier/prettier
    //watch 속성은 ref속성이 담아진 변수를 그대로 사용하여 감시하는 것이기 떄문에
    //value 속성이 필요 없다.
    // eslint-disable-next-line prettier/prettier
    watch(message, newValue => {
      console.log(newValue);
    });
    function changedMessage() {
      message.value = "good";
    }
    console.log(message.value);
    onMounted(() => {
      console.log(count.value);
    });
    return {
      count,
      doubleCount,
      increase,
      message,
      reversedMessage,
      changedMessage,
    };
  },
};
</script>
