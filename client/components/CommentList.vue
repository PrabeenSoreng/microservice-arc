<template>
  <div>
    <ul>
      <li v-for="comment in comments" :key="comment.id">
        {{ renderedComments(comment) }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    comments: Array
  },
  data() {
    return {};
  },
  methods: {
    renderedComments(comment) {
      // this.comments.map(comment => {
      let content;
      if (comment.status === "approved") content = comment.content;
      if (comment.status === "pending")
        content = "This comment is awaiting moderation.";
      if (comment.status === "rejected")
        content = "This comment has been rejected!";
      return content;
      // })
    }
  }
};
</script>
