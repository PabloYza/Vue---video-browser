<template>
  <div>
    <input v-on:input="onInput" /> <!-- v-on:  ===   @ -->
  </div>
</template>


<script>
export default {
  name: 'SearchBar',
  methods: {
    onInput(e) {  /* In order to send data from child to parent we create a FUNCTION that emits EVENTS */
      this.$emit('termChange', event.target.value);
    }
  }
};
</script>


<style>

</style>