<script setup lang="ts">
import ModalProvider from "./modals/ModalProvider.vue"
import Button from "./Button.vue"
</script>

<template>
  <ModalProvider>
    <Button></Button>
    随便放点东西
  </ModalProvider>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
