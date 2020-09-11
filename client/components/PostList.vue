<template>
  <div>
    <div v-for="post in posts" :key="post.id" class="card" style="width: 30%, margin-bottom: 20px">
      <div class="card-body">
        <h3>{{ post.title }}</h3>
        <CommentList :comments="post.comments" />
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
    return {};
  },
  props: {
    posts: Array,
  },
};
</script>
