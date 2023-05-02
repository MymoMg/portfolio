<script setup>

const props = defineProps({
    text: String,
    link: String,
})

</script>

<template>
    <NuxtLink :to="`/${link}`" class="button">{{ text }}</NuxtLink>
</template>

<style scoped>

.button {
    padding: 0.5rem 1.5rem;
    width: fit-content;
    background-color: red;
    border-radius: 100vmax;
}

</style>