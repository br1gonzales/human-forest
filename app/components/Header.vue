<script setup>
const repositoryUrl = "#"
</script>

<template>
    <header class="flex sticky top-0 w-full relative p-[12px_16px] items-center">
        <Logo />
        <NuxtLink class="ml-auto hover:underline" :to="repositoryUrl">repository</NuxtLink>
    </header>
</template>