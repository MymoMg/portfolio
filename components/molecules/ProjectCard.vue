<script setup>

const props = defineProps({
    project_name: String,
})

</script>

<template>
    <article>
        <NuxtLink :to="`${$route.href}/${project_name}`" class="cardLink">
            <img src="https://loremflickr.com/320/240?random=1"/>
            <h3>{{project_name.split("_").join(" ")}}</h3>
        </NuxtLink>
    </article>
</template>

<style scoped>
    
.cardLink {
    padding: 5rem 1.5rem 3rem 1.5rem;
    display: grid;
    gap: 1rem;
    width: fit-content;
    background-color: var(--secondary-color);
    display: grid;
    place-items: center;
    text-align: center;
    box-shadow: 0 0 10px rgba(0,0,0, 0.15);
    transition: transform .3s ease-in-out, box-shadow .4s;
}
.cardLink:is(:hover, :focus) {
    transform: scale(1.05);
    box-shadow: 0 0 10px rgba(0,0,0, 0.25);
}

.cardLink img{
    margin-bottom: 1.5rem;
    width: 35%;
}
</style>