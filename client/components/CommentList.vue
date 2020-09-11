<template>
  <div>
    <ul>
      <li v-for="comment in comments" :key="comment.id">{{ comment.content }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    comments: Array,
  },
  data() {
    return {};
  },
};
</script>
