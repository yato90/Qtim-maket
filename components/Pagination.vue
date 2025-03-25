<script setup lang="ts">
const props = defineProps({
    currentPage: {
        type: Number,
        required: true,
    },
    totalPages: {
        type: Number,
        required: true,
    },
    visiblePages: {
        type: Array as PropType<number[]>,
        required: true,
    },
});

const emit = defineEmits(["update:currentPage"]);

const goToPage = (page: number) => {
    emit("update:currentPage", page);
};

const prevPage = () => {
    if (props.currentPage > 1) {
        emit("update:currentPage", props.currentPage - 1);
    }
};

const nextPage = () => {
    if (props.currentPage < props.totalPages) {
        emit("update:currentPage", props.currentPage + 1);
    }
};
</script>
<template>
    <div class="pagination">
      <button class="page" @click="prevPage" :disabled="currentPage === 1"><img src="~/assets/Arrow.svg" alt="Arrow" style="transform: rotate(180deg);"></button>
      
      <button
        v-for="page in visiblePages"
        :key="page"
        @click="goToPage(page)"
        :class="{ active: currentPage === page }"
      >
        {{ page }}
      </button>
      
      <button class="page" @click="nextPage" :disabled="currentPage === totalPages"><img src="~/assets/Arrow.svg" alt="Arrow"></button>
    </div>
</template>
  
<style scoped>
.pagination {
    display: flex;
    gap: 8px;
    justify-content: start;
    align-items: center;
}

button {
    background-color: #f3f3f3;
    cursor: pointer;
    border-radius: 12px;
    padding: 11px 17px;
    border:none;
    font-weight: 400;
    font-size: 16px;
    line-height: 50%;
    width: 44px;
    height: 44px;
}
button:hover {
    opacity: 0.3;
}
button:disabled {
    background-color: #ccc;
}

button.active {
    color: #fff;
    background-color: #101010;
}
.page{
    background-color: #fff;
    border: 1px solid #dbdbdb;
}
</style>
  