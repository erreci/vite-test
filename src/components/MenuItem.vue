<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
    item: Object,
});

const emits = defineEmits(['click']);

const onClick = () => {
    emits('click', props.item.route, props.item.params);
};
</script>

<!-- MenuItem.vue -->
<template>
    <div @click="$emit('click', item.route)">
      <svg viewBox="0 0 24 24">
        <path :d="item.icon" />
      </svg>
    </div>
  </template>

<style scoped>
div {
  cursor: pointer;
  padding: 10px;
  border-bottom: 1px solid #ccc;
}

div:hover {
  background-color: #f0f0f0;
}

svg {
  width: 24px;
  height: 24px;
}
</style>