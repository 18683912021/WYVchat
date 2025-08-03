<template>
  <div class="flex items-center justify-between h-screen">
    <div class="w-[300px] bg-gray-200 h-full border-r border-gray=300">
      <ConversationList :items="items" />
    </div>
    <div class="h-full flex-1">content</div>
  </div>
</template>
<script setup lang="ts">
import { ConversationProps } from "./types";
import ConversationList from "./components/ConversationList.vue";
const items: ConversationProps[] = [
  {
    id: 1,
    title: "Conversation 1",
    selectedMode: "Mode 1",
    createdAt: "2021-01-01",
    updatedAt: "2021-01-01",
    rpoviderId: 1,
  },
  {
    id: 2,
    title: "Conversation 1",
    selectedMode: "Mode 1",
    createdAt: "2021-02-01",
    updatedAt: "2021-02-01",
    rpoviderId: 1,
  },
  {
    id: 3,
    title: "Conversation 2",
    selectedMode: "Mode 2",
    createdAt: "2021-01-01",
    updatedAt: "2021-01-01",
    rpoviderId: 2,
  },
  {
    id: 4,
    title: "Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2",
    selectedMode: "Mode 2",
    createdAt: "2021-01-01",
    updatedAt: "2021-01-01",
    rpoviderId: 2,
  },
];
</script>
