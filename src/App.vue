<script setup lang="ts">
import { useMagicKeys } from "@vueuse/core";
import { watch } from "vue";

const { Shift_X_Y_Z } = useMagicKeys();

function emitEmptyKeyboardEvent() {
  console.log("x");
  window.dispatchEvent(new KeyboardEvent("keyup"));
}

watch(Shift_X_Y_Z, () => {
  alert("hello world");
});
</script>

<template>
  <div class="flex items-center justify-center w-screen h-screen">
    <button @click="emitEmptyKeyboardEvent">Click me</button>
  </div>
</template>
