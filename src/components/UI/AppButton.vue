<template>
  <button class="button">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'app-button'
}
</script>

<style scoped>
.button {
  padding: 1rem 1.5rem;
  background: none;
  color: teal;
  border-color: teal;
  border-radius: 1rem;
  cursor: pointer;
  transition: background-color 300ms ease;
}
.button:hover{
  color: #ffffff;
  background: teal;
}
</style>