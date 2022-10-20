<template>
  <div>
    <div class="count">{{ count }}</div>
    <div class="label">{{ label }}</div>
  </div>
</template>

<script setup lang="ts">
  import { defineProps } from "vue";

  defineProps<{ count: String, label: String }>()
</script>

<style lang="scss" scoped>
  .count{
    font-size: 4rem;
    font-weight: 800;
  }
</style>