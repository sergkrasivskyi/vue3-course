<template>
  <div class="flow container">
    <h1>Сторінка з постами</h1>
    <app-button
    @click="showDialog"
    >Додати пост</app-button>
    <app-dialog v-model:show="isDialogVisible" >
      <post-form @createPost="addPost"/>
    </app-dialog>
    <post-list :posts="postsApp" @removePost="deletePost"></post-list>
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
      ],
      isDialogVisible: false,
    }
  },
  methods: {
    addPost(post) {
      this.postsApp.push(post),
      this.isDialogVisible = false
    },
    deletePost(post) {
      this.postsApp = this.postsApp.filter(elem => elem.id != post.id)
    },
    showDialog() {
      this.isDialogVisible = true;
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