<template>
  <div class="posts">
    <h1>Posts</h1>

    <ul>
      <li v-for="post in posts" :key="post.name">
        <RouterLink :to="`/postDetail/${ post.value }`"> {{ post.name }} </RouterLink>
      </li>
    </ul>

    <textarea v-autofocus></textarea>
  </div>
</template>

<script setup>
/*
  imports
*/
import { vAutofocus } from "@/directives/vAutofocus";
import { ref } from "vue";

/*
 posts
*/

const posts = ref([
  {
    name: "Post 1",
    value: "id1",
  },
  {
    name: "Post 2",
    value: "id2",
  },
  {
    name: "Post 3",
    value: "id3",
  },
]);
</script>

<style scoped>
ul {
  margin-bottom: 30px;
}
</style>
