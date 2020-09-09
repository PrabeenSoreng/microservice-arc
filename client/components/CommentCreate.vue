<template>
  <div>
    <form @submit.prevent="onSubmit">
      <div class="form-group">
        <label for="comment">New Comment</label>
        <input type="text" v-model="comment" id="comment" class="form-control" />
      </div>
      <button class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  props: {
    postId: String,
  },
  data() {
    return {
      comment: "",
    };
  },
  methods: {
    async onSubmit(postId) {
      await this.$axios.$post(
        `http://localhost:4001/posts/${this.postId}/comments`,
        {
          content: this.comment,
        }
      );
    },
  },
};
</script>