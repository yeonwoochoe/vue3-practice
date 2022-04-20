<template>
  <section v-if="hasFruit">
    <h1>Fruits</h1>
    <ul>
      <li v-for="fruit in fruits" :key="fruit">
        {{ fruit }}
      </li>
    </ul>
  </section>
  <section>
    <h1>Reverse Fruits</h1>
    <ul>
      <li v-for="fruit in reverseFruots" :key="fruit">
        {{ fruit }}
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      fruits: ["Apple", "Banana", "Cherry"],
    };
  },
  computed: {
    hasFruit() {
      return this.fruits.length > 0;
    },
    reverseFruots() {
      // eslint-disable-next-line prettier/prettier
      return this.fruits.map(fruit =>
        //'Apple' => ['A' ,'p','p','l','e'] => [ 'e', 'l', 'p' ,'p' ,'e'] => alppA
        fruit.split("").reverse().join("")
      );
    },
  },
};
</script>
