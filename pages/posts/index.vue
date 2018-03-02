<template>
  <div class="posts-page">
    <PostList :posts="loadedPosts" />
  </div>
</template>

<script>
import PostList from "@/components/Posts/PostList";

export default {
  components: {
    PostList
  },
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          loadedPosts: [
            {
              id: "1",
              title: "First Post",
              previewText: "This is my first post",
              thumbnailLink: "https://source.unsplash.com/random"
            },
            {
              id: "2",
              title: "Second Post",
              previewText: "This is my second post",
              thumbnailLink: "https://source.unsplash.com/random"
            }
          ]
        });
      }, 1000);
    }).then(data => {
      return data
    }).catch(e => {
      context.error(new Error());
    });
  },
  created() {
    this.$store.dispatch('setPosts', this.loadedPosts)
    console.log(this.$store)
  }
};
</script>


<style scoped>
.posts-page {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
