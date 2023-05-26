<template>
  <div class="flex rounded my-2 px-4 py-4 absolute" :class="{'justify-end': message.outgoing,'bg-blue-100 right-[1rem] mt-[1rem]':!message.outgoing,'bg-indigo-500 left-[1rem]  mt-[5rem]':message.outgoing}">
    <p>{{ message.text }}</p>
  </div>

</template>

<script setup>
 const props = defineProps(["message"]);
</script>

<style scoped>
div {
  width: fit-content;
  border-radius: 3rem;
}
</style>