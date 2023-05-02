<script setup>

import Button from '~/components/atoms/Button.vue';

</script>

<template>
    <section>
        <article>
            <div>
                <h1>Bienvenue sur mon portfolio</h1>
                <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Voluptas at eaque harum sit! Itaque culpa nostrum id rem nulla sequi, tempora modi eum expedita labore.  </p>
                <Button text="noir" />
            </div>
            <div>
                <img src="https://loremflickr.com/320/240?random=2"/>
            </div>
        </article>
    </section>
</template>

<style scoped>

section {
    display: grid;
    place-items: center;
    height: 100vh;

}

section > article {
    display: grid;
    place-items: center;
    gap: 5vh;
    padding: 2vh 5vw;
}
section img {
    width: 100%;
}
section > article > div:first-child {
    display: grid;
    gap: 5px;
}

section svg {
    position: absolute;
    bottom: 0;
    z-index: -1;
}

@media screen and (min-width: 700px) {
    section >  article{
        grid-template-columns: 1fr 1fr;
        width: 80%;
    }
}

</style>