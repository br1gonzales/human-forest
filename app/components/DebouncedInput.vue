<script setup>
import { refDebounced } from '@vueuse/core';
const value = ref('')
const debouncedValue = refDebounced(value, 2000)
</script>

<template>
    <input type="text" v-model="value">
    <p>
        Your debounced value is: {{ debouncedValue }}
    </p>
</template>