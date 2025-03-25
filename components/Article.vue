<script setup lang="ts">
defineProps<{
    image: string 
    preview: string
}>()

</script>

<template>
  <div class="post-card">
    <img :src="image" alt="Post Image" class="post-image">
    <p>{{ preview }}</p>
    <div class="read">
        <p>Read more</p>
    </div>
  </div>
</template>

<style scoped>  
.post-card { 
    display: flex;
    flex-direction: column;
    width: 280px;
    position: relative;
    transition: transform 0.3s ease-in-out, padding 0.3s ease-in-out;
    p{
        font-family: "TT Commons", sans-serif;
        font-weight: 400;
        font-size: 20px;
        line-height: 120%;
        color: #101010;
        text-decoration: none;
    }
}
.post-image { 
    width: 280px;
    height: 280px;
    background: #e2beff;
}
.read {
    visibility: hidden;
    opacity: 0;
    transition: opacity 0.3s ease-in-out; 
    p{
        color: #e2beff;
    }
}

.post-card:hover {
    transform: translateY(-10px);
}

.post-card:hover .read {
    visibility: visible;
    opacity: 1;
}
</style>