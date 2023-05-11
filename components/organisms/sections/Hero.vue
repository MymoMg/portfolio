<script setup>

import Button from '~/components/atoms/Button.vue';

const props = defineProps({
    heading: String,
    catchphrase: String,
})

</script>

<template>
    <section>
        <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
            <defs>
                <linearGradient id="grad1">
                    <stop offset="0%" stop-color="var(--primary-accent-color-variant)"/>
                    <stop offset="100%" stop-color="var(--secondary-accent-color-variant)"/>
                </linearGradient>
            </defs>

            <path fill="url(#grad1)" d="M30.6,-33.2C41.8,-34,54.5,-27.9,59.5,-18C64.5,-8.1,61.8,5.6,59.2,21C56.6,36.4,54,53.5,44.1,63.8C34.2,74,17.1,77.3,6.8,67.9C-3.5,58.6,-7,36.5,-16.7,26.2C-26.4,15.9,-42.4,17.4,-45.6,13.4C-48.8,9.4,-39.3,-0.1,-33.4,-8.6C-27.5,-17,-25.3,-24.3,-20.3,-25.5C-15.3,-26.6,-7.7,-21.6,1,-23C9.7,-24.4,19.4,-32.3,30.6,-33.2Z"/>
        </svg>
        <article>
            <div>
                <h1>{{heading}}</h1>
                <p>{{catchphrase}}</p>
                <Button text="noir" />
            </div>
            <div>
                <img src="/Meriem_Mguil.png"/>
            </div>
        </article>
    </section>
</template>

<style scoped>

section {
    display: grid;
    place-items: center;
    height: calc(100vh - var(--header-height));
    overflow: visible;
}

section > svg {
    position: absolute;
    z-index: -1;
    inset: 0;
}

section > svg path {
    transform: translate(75%, -10%) scale(1.4);
}

section > article {
    display: grid;
    place-items: center;
    align-self: flex-end;
    gap: 5vh;
    padding: var(--header-height) 5vw 0 5vw;
}
section img {
    width: 100%;
    height: 80vh;
    transform: scale(-1, -1);
    object-fit: cover;
    object-position: top center;

}
section > article > div:first-child {
    display: grid;
    gap: 5px;
}


@media screen and (min-width: 700px) {
    section >  article{
        grid-template-columns: 1fr 1fr;
        width: 80%;
    }
}

</style>