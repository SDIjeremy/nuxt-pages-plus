<script setup lang="ts">
const { stacks } = useModalRouter()
</script>

<template>
  <div>
    <output id="modal-stacks">{{ JSON.stringify(stacks ?? null) }}</output>
    <PlusModalNuxtPage />
  </div>
</template>
