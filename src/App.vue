<template>
  <header>
    <el-button type="primary" @click="openTestDialog">Test</el-button>
    <test-dialog ref="testDialog" />
  </header>
</template>

<script setup lang="ts">
import TestDialog from '@/views/TestDialog.vue'
import { useTemplateRef } from 'vue'

const testDialogRef = useTemplateRef('testDialog')

function openTestDialog() {
  testDialogRef.value?.open()
}
</script>

<style scoped></style>
