<script setup>
const props = defineProps('variant')
const classObject = ref({
    ' text-red-950 underline decoration-indigo-500 decoration-4 font-bold hover:text-red-900': true,
    'text-[40px]': props.variant === 'h1'
})
</script>
<template>
    <p :class="classObject">
        <slot />
    </p>
</template>