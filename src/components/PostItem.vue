<template>
  <div class="post">
    <div><strong>Назва: </strong>{{postItem.title}}</div>
    <div><strong>Текст: </strong>{{postItem.body}}</div>
  </div>
</template>

<script>
export default {
  props: {
    postItem: {
      type: Object,
      reqiured: true
    }
  },
}
</script>

<style scoped>
.post {
  padding: 1rem;
  border: 2px solid teal;
}
</style>