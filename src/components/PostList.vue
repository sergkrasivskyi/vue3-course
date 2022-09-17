<template>
  <div> 
    <h3>Список користувачів</h3>
      <post-item v-for="post in posts" :key="post.id" :postItem="post"/>
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
  }

}
</script>

<style scoped>

</style>