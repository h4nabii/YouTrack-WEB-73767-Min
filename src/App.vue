<template>
  <header>
    <el-button type="primary" @click="openTestDialog">Test</el-button>
    <test-dialog ref="testDialog" />
    <div>{{ a1 }}</div>
  </header>
</template>

<script setup lang="ts">
import TestDialog from '@/views/TestDialog.vue'
import { useTemplateRef, ref } from 'vue'

const testDialogRef = useTemplateRef('testDialog')

const a1 = ref(1)

function openTestDialog() {
  testDialogRef.value?.open()
}
</script>

<style scoped></style>
