<script setup>

import ChatList from "./components/ChatList.vue";
import {ref} from "vue";

const conversations = ref([]);

conversations.value.push({
  title: "Chat with HASSAN",
  messages: [
    {
      outgoing: true,
      text: "Hello, HASSAN!",
      username: "7AYDER"
    },
    {
      outgoing: false,
      text: "Hello, Haidar!",
      username: "azeez"
    },

  ]
})
conversations.value.push({
  title: "Chat with Ahmed",
  messages: [
    {
      outgoing: true,
      text: "HELLO AHMED",
      username: "HAYD#))@"
    },
    {
      outgoing: false,
      text: "Hello, Haidar!",
      username: "azeez"
    },

  ]
})

</script>
<template>

  <div class="container flex mx-auto justify-center">
    <chat-list :conversations="conversations"></chat-list>
  </div>
</template>
