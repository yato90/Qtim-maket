<script setup lang="ts">
import { ref, computed } from "vue";
import type { BlogPost } from "@/types/blog";
import Article from "~/components/Article.vue";
import Pagination from "~/components/Pagination.vue";

const currentPage = ref(1);
const perPage = 8;

const { data: posts } = await useFetch<BlogPost[]>("https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/");

const paginatedPosts = computed(() =>
  posts.value?.slice((currentPage.value - 1) * perPage, currentPage.value * perPage)
);

const totalPages = computed(() => (posts.value ? Math.ceil(posts.value.length / perPage) : 1));

const visiblePages = computed(() => {
  const pages = [];
  const startPage = Math.max(1, currentPage.value - 2);
  const endPage = Math.min(totalPages.value, startPage + 4);

  for (let i = startPage; i <= endPage; i++) {
    pages.push(i);
  }
  return pages;
});
</script>

<template>
  <div class="container">
    <h2>Articles</h2>
    <div class="posts">
      <NuxtLink v-for="post in paginatedPosts" :key="post.id" :to="`/post/${post.id}`">
        <Article :image="post.image" :preview="post.preview"/>
      </NuxtLink>
    </div>

    <Pagination
      :currentPage="currentPage"
      :totalPages="totalPages"
      :visiblePages="visiblePages"
      @update:currentPage="currentPage = $event"
    />
  </div>
</template>

<style scoped>
h2{
    font-weight: 400;
    font-size: 84px;
    line-height: 100%;
    color: #101010;
}
a{
    text-decoration: none;
}
.container { 
    display: flex;
    flex-direction: column;
    gap: 50px;
    margin: 0 112px; 
}
.posts { 
    display: flex;
    flex-wrap: wrap;
    gap: 32px; 
}
</style>