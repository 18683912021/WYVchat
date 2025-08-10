<template>
  <div
    class="h-[10%] bg-gray-200 border-b border-gray-300 flex items-center px-3 justify-between"
    v-if="conversation"
  >
    <h3 class="font-semibold text-gray-900">{{ conversation?.title }}</h3>
    <span class="text-sm text-gray-500">{{ conversation.updatedAt }}</span>
  </div>
  <div class="w-[80%] mx-auto h-[85%] overflow-y-auto pt-2">
    <MessageList :messages="filteredMessages" />
  </div>
  <div class="w-[80%] mx-auto h-[15%] flex items-center">
    <MessageInput />
  </div>
</template>
<script setup lang="ts">
import { useRoute } from "vue-router";
import MessageList from "../components/MessageList.vue";
import MessageInput from "../components/MessageInput.vue";
import { conversations, messages } from "../testData";
import { ref, watch } from "vue";
import { ConversationProps, MessageProps } from "../types";
const route = useRoute();
const filteredMessages = ref<MessageProps[]>([]);
const conversation = ref<ConversationProps>();
let conversationId = parseInt(route.params.id as string);
conversation.value = conversations.find(
  (conversation) => conversation.id === conversationId
);
filteredMessages.value = messages.filter(
  (message) => message.conversationId === conversationId
);
watch(
  () => route.params.id,
  (newId: string) => {
    conversationId = parseInt(newId);
    conversation.value = conversations.find(
      (conversation) => conversation.id === conversationId
    );
    filteredMessages.value = messages.filter(
      (message) => message.conversationId === parseInt(newId)
    );
  }
);
</script>
