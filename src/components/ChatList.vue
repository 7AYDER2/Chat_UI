<template>
  <div class="flex gap-2 text-black w-full m-4">
    <div class="flex flex-col w-1/5 bg-blue-200 rounded p-3">
      <div class="flex gap-3 mb-4">
            <svg xmlns="http://www.w3.org/2000/svg" fill="royalblue" viewBox="0 0 24 24" stroke-width="1.5" stroke="none" class="w-6 h-6">
               <path stroke-linecap="round" stroke-linejoin="round" d="M20.25 8.511c.884.284 1.5 1.128 1.5 2.097v4.286c0 1.136-.847 2.1-1.98 2.193-.34.027-.68.052-1.02.072v3.091l-3-3c-1.354 0-2.694-.055-4.02-.163a2.115 2.115 0 01-.825-.242m9.345-8.334a2.126 2.126 0 00-.476-.095 48.64 48.64 0 00-8.048 0c-1.131.094-1.976 1.057-1.976 2.192v4.286c0 .837.46 1.58 1.155 1.951m9.345-8.334V6.637c0-1.621-1.152-3.026-2.76-3.235A48.455 48.455 0 0011.25 3c-2.115 0-4.198.137-6.24.402-1.608.209-2.76 1.614-2.76 3.235v6.226c0 1.621 1.152 3.026 2.76 3.235.577.075 1.157.14 1.74.194V21l4.155-4.155" />
           </svg>
          <h2 class="font-bold text-white">Message4You</h2>
        </div>
      <div @click="selectedConversationIndex = index" v-for="(conversation,index) in conversations"
           class="p-2 rounded-lg m-1 cursor-pointer hover:bg-sky-200">
        <span class="font-bold">{{ conversation.title }}</span>
      </div>
    </div>
    <div class="flex flex-col w-4/5 bg-white rounded h-[90vh]">
      <div v-if="currentConversation != null" class="flex flex-col w-full px-2 relative">
        <chat-bubble v-for="message in currentConversation.messages" :message="message"></chat-bubble>
      </div>
      <div v-else class="justify-center items-center h-full w-full">
        <span class="flex h-[90vh] justify-center items-center font-bold text-4xl">Please select a conversation first. 😁</span>
      </div>
    </div>

  </div>
</template>

<script setup>
import {computed, ref} from "vue";
import ChatBubble from "../components/ChatPopup.vue";

const props = defineProps({
  conversations: {
    type: [Array],
    required: true,
  }
})
const selectedConversationIndex = ref();
const currentConversation = computed(() => {
  return props.conversations[selectedConversationIndex.value];
});
</script>