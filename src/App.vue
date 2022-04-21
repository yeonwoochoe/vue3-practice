<template>
  <MyBtn text="포도" style="border-radius: 30px" />
  <MyBtn color="red">사과</MyBtn>
  <MyBtn color="#404040">딸기</MyBtn>
  <MyBtn :color="color">파인애플</MyBtn>
  <MyBtn large color="royalblue">블루베리</MyBtn>
  <MyBtn>Apple</MyBtn>
  <MyBtn :color="color"><span style="color: red">lemon</span></MyBtn>

  <button>Banana</button>
</template>

<script>
//부모자식간의 데이터 통신
import MyBtn from "~/components/MyBtn.vue";

export default {
  components: {
    MyBtn,
  },
  data() {
    return {
      color: "#000",
    };
  },
};
</script>
