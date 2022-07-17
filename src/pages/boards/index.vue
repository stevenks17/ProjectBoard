<script setup lang="ts">
import { ref } from "vue";
import { Board } from "@/types"
const boards = ref<Partial<Board>[]>([
    {
        id: "1",
        title: "First Board",
        order:"[]",
        image: {
            downloadUrl: "https://picsum.photos/480/270?board=1",
        },
    },
        {
        id: "2",
        title: "Second Board",
        order:"[]",
    },
        {
        id: "3",
        title: "Third Board",
        order:"[]",
    },
])
</script>
<template>
  <h1 class="text-3xl mb-5">Boards</h1>
  <div class="flex">
    <BoardCard v-for="board in boards" :key="board.id" :board="board" />
    <button class="text-gray-500" @click="createBoard(newBoardTemplate)">
      <span>New Board +</span>
    </button>
  </div>
</template>
