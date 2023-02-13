<template>
  <p>Counter: {{ trackCounter }}</p>
  <button @click="incrementCounter">Increment</button>
</template>

<script>
export default {
  methods: {
    incrementCounter() {
      this.$store.dispatch("increment", 1);
    },
  },
  computed: {
    trackCounter() {
      return this.$store.getters.getCounter;
    },
  },
};
</script>
