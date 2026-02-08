<script setup>
const repositoryUrl = "https://github.com/br1gonzales/human-forest"
</script>

<template>
    <header class="flex sticky top-0 w-full relative p-[12px_16px] items-center">
        <Logo />
        <NuxtLink target="_blank" class="ml-auto hover:underline" :to="repositoryUrl">
            <Text>Visit repository</Text>
        </NuxtLink>
    </header>
</template>