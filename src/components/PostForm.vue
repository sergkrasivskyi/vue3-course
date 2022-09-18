<template>
  <form>
    <h4>Create Post</h4>
    <app-input placeholder="Введіть назву посту" v-model="post.title"/>
    <app-input placeholder="Введіть текст посту" v-model="post.body"/>
    <app-button class="form-button" @click="createPost" type="button">Add post</app-button>
  </form>
</template>

<script>
import { computed } from '@vue/runtime-core'
export default {
  data() {
    return {
      post: { title: '', body: '' }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('createPost', this.post)
      this.post = { title: '', body: '' }

    }
  },
}
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}
.form-button {
  margin-top: 1rem;
  align-self: flex-start;
}

</style>