<template>
  <div>
    <div v-for="post in posts" :key="post.id" class="card" style="width: 30%, margin-bottom: 20px">
      <div class="card-body">
        <h3>{{ post.title }}</h3>
        <CommentList :postId="post.id" />
        <hr />
        <CommentCreate :postId="post.id" />
      </div>
    </div>
  </div>
</template>

<script>
import CommentCreate from "~/components/CommentCreate";
import CommentList from "~/components/CommentList";
export default {
  components: {
    CommentCreate,
    CommentList,
  },
  data() {
    return {
      // comments: [],
    };
  },
  props: {
    posts: Array,
  },
  // async created() {
  //   this.posts.map(async (post) => {
  //     this.comments = await this.$axios.$get(
  //       `http://localhost:4001/posts/${post.id}/comments`
  //     );
  //     console.log(this.comments);
  //   });
  // },
};
</script>