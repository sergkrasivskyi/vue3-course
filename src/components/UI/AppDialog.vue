<template>
  <div class="dialog" v-if="show" @click="hideDialog">
    <div @click.stop class="dialog__content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app-dialog',
  props: {
    show: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    hideDialog() {
      this.$emit("update:show", false)
    }
  }

}
</script>

<style scoped>
.dialog {
  inset: 0;
  background-color: rgba(15, 48, 48, 0.5);
  position: fixed;
  display: flex;
}
.dialog__content {
  margin: auto;
  padding: 1rem;
  background-color: bisque;
  border-radius: 1rem;
}
</style>