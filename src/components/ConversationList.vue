<template>
  <div class="conversation-liat">
    <div
      class="item border-gray-300 border-t cursor-pointer bg-white hover:bg-gray-200 p-2"
      v-for="item in items"
      :key="item.id"
    >
      <a href="#" @click="goToConversation(item.id)">
        <div
          class="flex justify-between items-center text-sm leading-5 test gray-500"
        >
          <span>{{ item.selectedModel }}</span>
          <span>{{ item.updatedAt }}</span>
        </div>
        <h2 class="font-semibold text-gray-900 truncate">{{ item.title }}</h2>
      </a>
    </div>
  </div>
</template>

<script setup lang="ts">
import { useRouter } from "vue-router";
import { ConversationProps } from "../types";
defineProps<{ items: ConversationProps[] }>();
const router = useRouter();
const goToConversation = (id: number) => {
  router.push(`/conversation/${id}`);
};
</script>
