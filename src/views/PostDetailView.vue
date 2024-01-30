<template>
  <div class="post-detail">
    <h1>This is a post page</h1>
    <p>Display the content of post with ID of {{ $route.params.id }} here!</p>
    <div>
      <button @click="showPostId">Show POst ID</button>
    </div>
    <div>
      <button @click="goHomeIn3Seconds">Go to Home in 3 seconds</button>
    </div>
    <div>
      <button @click="goTofirstPost">Go to First post</button>
    </div>
    <p><RouterLink to="/posts">&lt; Back</RouterLink></p>
  </div>
</template>

<script setup>
import { useRoute, useRouter } from "vue-router";

/*
  imports
*/
const route = useRoute();
const router = useRouter();

const showPostId = () => {
  alert(`The ID of this post is: ${route.params.id}`);
};

const goHomeIn3Seconds = () => {
  setTimeout(() => {
    router.push({ name: "home" });
  }, 3000);
};
const goTofirstPost = () => {
  router.push({ name: "postDetail", params: { id: "id1" } });
};
</script>
