<template>
  <input class="input" type="text" :value="modelValue" @input="updateInput">
</template>

<script>
export default {
  name: 'app-input',
  props: {
  modelValue:[String, Number]
  },
  data() {

    return {
    }
  },
  methods: {
    updateInput(event) {
      this.$emit('update:modelValue', event.target.value)
    }
  },

}
</script>

<style scoped>
.input {
  width: 100%;
  padding: 1rem;
  border: 2px solid teal;
  border-radius: 1rem;
}
</style>