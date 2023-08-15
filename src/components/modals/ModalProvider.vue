<template>
  <slot />

  <TestModal
    v-bind="allTestModalProps"
    @update:show="handleTestModalUpdateShow"
    @close="closeTestModalCallback"
    @confirm="confirmTestModalCallback"
    @cancel="cancelTestModalCallback"
  />
  <SecondModal
    v-bind="allSecondModalProps"
    @update:show="handleSecondModalUpdateShow"
    @close="closeSecondModalCallback"
    @confirm="confirmSecondModalCallback"
    @cancel="cancelSecondModalCallback"
  />
  <!-- 新增Modal -->
</template>

<script setup lang="ts">
import TestModal from "./test-modal/TestModal.vue";
import { provideTestModal } from "./test-modal/use-test-modal";
import SecondModal from "./second-modal/SecondModal.vue";
import { provideSecondModal } from "./second-modal/use-second-modal";
/** 新增import */

const {
  allProps: allTestModalProps,
  handleUpdateShow: handleTestModalUpdateShow,
  closeCallback: closeTestModalCallback,
  confirmCallback: confirmTestModalCallback,
  cancelCallback: cancelTestModalCallback,
} = provideTestModal();
const {
  allProps: allSecondModalProps,
  handleUpdateShow: handleSecondModalUpdateShow,
  closeCallback: closeSecondModalCallback,
  confirmCallback: confirmSecondModalCallback,
  cancelCallback: cancelSecondModalCallback,
} = provideSecondModal();
/** 新增provide */
</script>
