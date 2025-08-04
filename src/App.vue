<template>
  <div class="flex items-center justify-between h-screen">
    <div class="w-[300px] bg-gray-200 h-full border-r border-gray=300">
      <div class="h-[90%] overflow-y-auto">
        <ConversationList :items="items" />
      </div>
      <div class="h-[10%] grid grid-cols-2 gap-2 p-2">
        <RouterLink to="/conversation">
          <button
            class="shoadow-sm inline-flex items-center justify-center bg-green-700 text-white hover:bg-green-700/90 border border-green-700 h-[32px] py-[8px] px-[15px] text-sm rounded-[4px]"
          >
            <Icon
              icon="radix-icons:chat-bubble"
              width="15"
              height="15"
              class="mr-2"
            ></Icon>
            新建聊天
          </button>
        </RouterLink>

        <RouterLink to="/settings">
          <button
            class="shoadow-sm inline-flex items-center justify-center bg-green-50 text-green-700 hover:bg-green-700 border border-green-700 hover:text-white h-[32px] py-[8px] px-[15px] text-sm rounded-[4px]"
          >
            <Icon
              icon="radix-icons:gear"
              width="15"
              height="15"
              class="mr-2"
            ></Icon>
            应用设置
          </button>
        </RouterLink>
      </div>
    </div>
    <div class="h-full flex-1">
      <RouterView />
    </div>
  </div>
</template>
<script setup lang="ts">
import { Icon } from "@iconify/vue";
import { ConversationProps, ProviderProps } from "./types";
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
    title:
      "Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2",
    selectedMode: "Mode 2",
    createdAt: "2021-01-01",
    updatedAt: "2021-01-01",
    rpoviderId: 2,
  },
  {
    id: 5,
    title:
      "Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2",
    selectedMode: "Mode 2",
    createdAt: "2021-01-01",
    updatedAt: "2021-01-01",
    rpoviderId: 2,
  },
  {
    id: 6,
    title:
      "Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2",
    selectedMode: "Mode 2",
    createdAt: "2021-01-01",
    updatedAt: "2021-01-01",
    rpoviderId: 2,
  },
  {
    id: 7,
    title:
      "Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2",
    selectedMode: "Mode 2",
    createdAt: "2021-01-01",
    updatedAt: "2021-01-01",
    rpoviderId: 2,
  },
  {
    id: 8,
    title:
      "Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2Conversation 2",
    selectedMode: "Mode 2",
    createdAt: "2021-01-01",
    updatedAt: "2021-01-01",
    rpoviderId: 2,
  },
];
</script>
