<template>
  <div class="posts-page">
    <section class="posts-list">
      <PostPreview
      id="1"
      thumbnail="https://source.unsplash.com/random"
      title="hello there!"
      previewText="this is my first post"
      />
      <PostPreview
      id="3"
      thumbnail="https://source.unsplash.com/random"
      title="hello Bob!"
      previewText="this is my second post"
      />
      <PostPreview
      id="3"
      thumbnail="https://source.unsplash.com/random"
      title="hello steve!"
      previewText="this is my third post"
      />
    </section>
  </div>
</template>

<script>
import PostPreview from './PostPreview.vue'
export default {
  components: {
    PostPreview
  }
}
</script>


<style scoped>
.posts-page {
  display: flex;
  justify-content: center;
  align-items: center;
}

.posts-list {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}

</style>
