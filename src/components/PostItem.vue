<template>
  <div class="post">
    <div class="post__item">
      <div><strong>Назва: </strong>{{postItem.title}}</div>
      <div><strong>Текст: </strong>{{postItem.body}}</div>
    </div>
    <app-button class="post__button" @click="$emit('removePost', postItem)">Delete</app-button>
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
  metods: {
  }
}
</script>

<style scoped>
.post {
  padding: 1rem;

  border: 2px solid teal;
  border-radius: 1rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.post__item, .post__button {
  margin: 0;
}
</style>