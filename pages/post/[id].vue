<script setup lang="ts">
import { useRoute } from "nuxt/app";
import type { BlogPost } from "@/types/blog";

const route = useRoute();
const { data: post } = await useFetch<BlogPost>(`https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/${route.params.id}`);
</script>

<template>
    <div v-if="post" class="container">
        <h2>{{ post.title }}</h2>
        <img :src="post.image" alt="Post Image" class="post-image">
        <div class="details">
            <p style="font-size: 16px;">About</p>
            <p>{{ post.description }}</p>
        </div>
    </div>
</template>

<style scoped>
h2{
    font-family: "TT Commons", sans-serif;
    font-weight: 400;
    font-size: 84px;
    line-height: 100%;
    color: #101010;
}
p{
    font-family: "TT Commons", sans-serif;
    font-weight: 400;
    font-size: 36px;
    line-height: 124%;
    color: #101010;
    margin: 0;
}
.container { 
    display: flex;
    flex-direction: column;
    gap: 80px;
    margin: 0 112px; 
}
.post-image { 
    width: 100%;
    height: 700px;
    background: #e2beff;
}
.details{
    display: flex;
    flex-direction: column;
    gap: 32px;
}
</style>