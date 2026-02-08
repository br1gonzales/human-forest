<script setup>
const props = defineProps('variant')
const classObject = ref({
    'font-medium': true,
    'text-[40px]': props.variant === 'h1'
})
</script>
<template>
    <p :class="classObject">
        <slot />
    </p>
</template>