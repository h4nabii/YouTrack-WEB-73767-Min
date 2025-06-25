<template>
  <el-dialog v-model="visible" :title @closed="onClosed">
    <template #default>
      <div></div>
      <div class="flex justify-end mt-10px">
        <el-button @click="close">Cancel</el-button>
        <el-button type="success" @click="submit">OK</el-button>
      </div>
    </template>
  </el-dialog>
</template>

<script setup lang="ts">
import { ref } from "vue";

const emits = defineEmits<{
  submit: [];
}>();

const visible = ref(false);
const title = ref("test");

async function loadData() {}

async function submit() {
  emits("submit");
  close();
}

async function open() {
  await loadData();
  visible.value = true;
}

function close() {
  visible.value = false;
}

function onClosed() {}

defineExpose({ open, close });
</script>

<style scoped lang="scss"></style>
