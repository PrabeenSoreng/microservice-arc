<template>
  <div>
    <form @submit.prevent="onSubmit">
      <div class="form-group">
        <label for="title">Title</label>
        <input v-model="title" type="text" id="title" class="form-control" />
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: ""
    };
  },
  methods: {
    async onSubmit() {
      await this.$axios.$post(`http://localhost:4000/posts`, {
        title: this.title
      });
      // const posts = Object.values(
      //   await this.$axios.$get("http://localhost:4000/posts")
      // );
      // this.$emit("newpost", posts);
      this.title = "";
    }
  }
};
</script>
