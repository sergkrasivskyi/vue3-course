<template>
  <div v-if="posts.length > 0">
    <h3>Список постов</h3>
    <post-item v-for="post in posts" :key="post.id" :postItem="post" @removePost="$emit('removePost', post)" />
  </div>
  <div v-else>
    <h3 class="empty-list">Список постів порожній</h3>
  </div>
</template>

<script>
import PostItem from '@/components/PostItem.vue';
export default {
  components: {
    PostItem
  },
  props: {
    posts: {
      type: Array,
      default: [],
      required: true
    }
  },
  methods: {
    deletePost(post) {
      $this.$emit('removePost', post)
    }
  },


}
</script>

<style scoped>
  .empty-list {
    color: tomato;
    font-weight: 900;
  }

</style>