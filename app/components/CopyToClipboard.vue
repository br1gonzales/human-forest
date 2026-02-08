<script setup>
import { useClipboard } from '@vueuse/core';
const source = ref('123456789')
const { text, copy, copied, isSupported } = useClipboard({ source: source.value })
</script>

<template>
    <section v-if="isSupported">
        <input type="text" class="bg-gray-100 p-[16px_10px] rounded-[2px]" :value="source" readonly>
        <Button @click="copy()">
            <small v-if="!copied" class="capitalize">copy number</small>
            <small v-else class="capitalize">copied!</small>
        </Button>

    </section>
    <span v-else>
        Your browser does not supports copying content to your clipboard.
    </span>
</template>