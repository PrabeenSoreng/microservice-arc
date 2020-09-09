<template>
  <div>
    <ul>
      <li v-for="comment in comments" :key="comment.id">{{comment.content}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    postId: String,
  },
  data() {
    return {
      comments: [],
    };
  },
  async created() {
    this.comments = await this.$axios.$get(
      `http://localhost:4001/posts/${this.postId}/comments`
    );
    console.log(this.comments);
  },
};
</script>