<template>
  <div class="w-[80%] mx-auto h-full">
    <div class="flex items-center h-[85%]">
      <ProviderSelect :items="providers" v-model="selectedMode" />
    </div>
    <div class="flex items-center h-[15%]">
      <MessageInput @create="createConversation" />
    </div>
  </div>
</template>
<script setup lang="ts">
import { computed, onMounted, ref } from "vue";
import ProviderSelect from "../components/ProviderSelect.vue";
import MessageInput from "../components/MessageInput.vue";
import { ProviderProps } from "src/types";
import { db } from "../../src/db";
import { useRouter } from "vue-router";
const router = useRouter();
const currentProvider = ref("");
const providers = ref<ProviderProps[]>([]);
const selectedMode = ref<string>("");
onMounted(async () => {
  providers.value = await db.providers.toArray();
});
const modelInfo = computed(() => {
  const [providerId, selectedMode] = currentProvider.value.split("/");
  return {
    providerId: parseInt(providerId),
    selectedMode,
  };
});
const createConversation = async (question: string) => {
  const { providerId, selectedMode } = modelInfo.value;
  const currentDate = new Date().toISOString();
  const conversationId = await db.conversations.add({
    title: question,
    providerId,
    selectedModel: selectedMode,
    createdAt: currentDate,
    updatedAt: currentDate,
  })
  const newMessageId = await db.messages.add({
    conversationId,
    type: "question",
    content: question,
    createdAt: currentDate,
    updatedAt: currentDate,
  })

router.push(`/conversation/${conversationId}?init=${newMessageId}`)
};
</script>
