<template>
  <h1>Projects lists</h1>
  <div v-for="post in posts" :key="post.id">
    <SingleProject :post="post"></SingleProject>
  </div>
</template>

<script>
import SingleProject from "./SingleProject";
export default {
  components: {
    SingleProject,
  },
  props: ["posts"],
  setup(props) {},
};
</script>
<style >
</style>


