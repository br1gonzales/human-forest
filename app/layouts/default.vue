<script setup>
import { useRefHistory } from '@vueuse/core';
const counter = ref(0)
const { history, undo, redo } = useRefHistory(counter, {
    deep: true,
    limit: 10
})
const value = ref('')
</script>

<template>
    <main class="flex flex-col">
        <Header />
        <NuxtPage />
        <section>
            <Text variant="h1">{{ counter }}</Text>
            <Row>
                <Button @click="counter++">add</Button>
                <Button @click="counter--">substract</Button>
            </Row>
            <Row>
                <Button @click="undo">undo</Button>
                <Button @click="redo">redo</Button>
            </Row>
        </section>
    </main>
</template>