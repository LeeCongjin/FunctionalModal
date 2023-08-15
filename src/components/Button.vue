<template>
  <n-button @click="open">打开test</n-button>
  <n-button @click="openSecondModal">打开second</n-button>
</template>
<script setup lang="ts">
import { injectSecondModal } from "./modals/second-modal/use-second-modal"
import { injectTestModal } from "./modals/test-modal/use-test-modal"

const modal = injectTestModal()
const secondModal = injectSecondModal()
function open() {
  modal?.open({
    inputValue: "我是test弹窗",
    onConfirm({ formData }, close, endLoading) {
      console.log({ ...formData })
      endLoading()
      close()
    },
  })
}
function openSecondModal() {
  secondModal?.open({
    inputValue: "我是第二个弹窗",
    onConfirm({ formData }, close, endLoading) {
      console.log({ ...formData })
      endLoading()
      close()
    },
  })
}
</script>
