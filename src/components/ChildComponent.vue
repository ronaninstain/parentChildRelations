<template>
  <div class="p-4 border rounded">
    <h2 class="text-lg font-bold mb-2">Child Component</h2>
    <p>Received Message: {{ message }}</p>
    <button class="bg-blue-500 text-white px-2 py-1 mt-2" @click="emitMessage">
      Emit Message
    </button>
  </div>
</template>

<script setup>
import { ref, defineProps, defineEmits } from "vue";

const props = defineProps({
  message: String,
});

const emit = defineEmits();

const emitMessage = () => {
  emit("messageEmitted", "Custom message from Child");
};
</script>

<style>
/* Tailwind CSS classes can be added here */
</style>
