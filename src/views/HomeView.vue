<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">toggle posts</button>
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import { ref } from "vue";

export default {
  name: "HomeView",
  components: { PostList },
  setup() {
    const posts = ref([
      {
        title: "Welcome to the blog",
        body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Impedit unde, quia fugit possimus velit eaque doloribus assumenda itaque commodi, ducimus, quis neque qui sit consequuntur quod. Ipsam, quis impedit.",
        id: 1,
      },
      {
        title: "Top 5 CSS tips",
        body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Impedit unde, quia fugit possimus velit eaque doloribus assumenda itaque commodi, ducimus, quis neque qui sit consequuntur quod. Ipsam, quis impedit. Numquam!",
        id: 2,
      },
    ]);

    const showPosts = ref(true);

    return { posts, showPosts };
  },
};
</script>
