<template>
  <button @click="one($event), two($event)">Submit</button>
</template>

<script>
export default {
  methods: {
    one(event) {
      console.log(event);
    },
    two(event) {
      console.log(event);
    },
  },
};
</script>
