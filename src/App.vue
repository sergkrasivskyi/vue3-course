<template>
  <div class="flow container">
    <post-form @createPost="addPost"></post-form>
    <post-list :posts="postsApp"></post-list>
  </div>
</template>

<script>
import PostForm from '@/components/PostForm.vue'
import PostList from '@/components/PostList.vue'
export default {
  components: {
    PostForm, PostList
  },
  data() {
    return {
      postsApp: [
        { id: 1, title: "Назва 1", body: "Пост про Javascript 1" },
        { id: 2, title: "Назва 2", body: "Пост про Javascript 2" },
        { id: 3, title: "Назва 3", body: "Пост про Javascript 3" },
        { id: 4, title: "Назва 4", body: "Пост про Javascript 4" }
      ]
    }
  },
  methods: {
    addPost(post) {
    this.postsApp.push(post)
    }
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:where(.flow :not(:first-child, div+div), div[class]) {
  margin-top: 1.2rem;
}

.container {
  padding: 2rem;
}
</style>