<template>
  <div class="container">
    <h1>Create Post</h1>
    <PostCreate @newpost="newPost($event)" />
    <hr />
    <h1>Posts</h1>
    <PostList :posts="posts" />
  </div>
</template>

<script>
import PostCreate from "~/components/PostCreate";
import PostList from "~/components/PostList";
export default {
  components: {
    PostCreate,
    PostList,
  },
  data() {
    return {
      posts: [],
    };
  },
  async created() {
    this.posts = Object.values(
      await this.$axios.$get("http://localhost:4000/posts")
    );
  },
  methods: {
    newPost(newpost) {
      this.posts = newpost;
      console.log(newpost);
    },
  },
};
</script>

<style>
</style>
