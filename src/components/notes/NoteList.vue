<script setup>
import Note from './Note.vue';

defineProps({
  notes: Object,
});
</script>

<template>
  <Note v-for="note in notes" :note="note" />
</template>
