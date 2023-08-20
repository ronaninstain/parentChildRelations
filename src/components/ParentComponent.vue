<template>
  <div class="p-4">
    <h2 class="text-xl font-bold mb-2">Parent Component</h2>
    <p>Message from Child Component: {{ receivedMessage }}</p>
    <ChildComponent
      :message="parentMessage"
      @messageEmitted="handleMessageEmitted"
    />
  </div>
</template>

<script setup>
import { ref } from "vue";
import ChildComponent from "./ChildComponent.vue";

const parentMessage = ref("Hello from Parent");

const receivedMessage = ref("");

const handleMessageEmitted = (message) => {
  receivedMessage.value = message;
};
</script>

<style>
/* Tailwind CSS classes can be added here */
</style>
