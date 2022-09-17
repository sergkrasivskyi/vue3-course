<template>
  <form>
    <h4>Create Post</h4>
    <input class="input" type="text" placeholder="Введіть назву посту" v-model.lazy="post.title">
    <input class="input" type="text" placeholder="Введіть текст посту" v-model.lazy="post.body">
    <button class="button" @click="createPost" type="button">Add post</button>
  </form>
</template>

<script>
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
  }
}
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}

.input {
  width: 100%;
  padding: 1rem;
  border: 2px solid teal;
}

.button {
  padding: 1rem 1.5rem;
  align-self: flex-start;
  background: none;
  color: teal;
  border-color: teal;
  border-radius: 1rem;
  cursor: pointer;
}
</style>