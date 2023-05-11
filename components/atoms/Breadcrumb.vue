<script setup>

const props = defineProps({
    fullUrl: String
})
const urls = props.fullUrl.split('/')
</script>

<template >
    <nav class="breadCrumb">
        <ul>
            <li v-for="(link, index) in urls">
                <NuxtLink :to="`${urls[index - 1] ? '/' + urls[index - 1] : ''}/${link}`" class="link">{{ link === '' ? 'Home' : link.split('_').join(' ') }}</NuxtLink>
            </li>
        </ul>
    </nav>
</template>

<style scoped>

.breadCrumb ul {
    display: flex;
    gap: 1.5rem;
}

.breadCrumb ul li {
    position: relative;
    text-transform: capitalize;
    font-size: 1.2rem;
    letter-spacing: 2px;
    font-weight: 500;
}

.breadCrumb ul li:not(:last-child)::after {
    content: '>';
    position: absolute;
    right: -0.75rem;
    top: 50%;
    transform: translate(50%, -50%);
}
.breadCrumb ul .link {
    text-decoration: underline;
}
</style>
