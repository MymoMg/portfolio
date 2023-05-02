<script setup>

import Card from '~/components/molecules/Card.vue';
import CardTest from '~/components/molecules/CardTest.vue';
</script>


<template>
    <section>
        <h2>Mes projets</h2>
        <div class="container">
            <CardTest />    
            <Card class="element"/>
            <Card class="element"/>
            <Card class="element"/>
        </div>
    </section>
</template>


<style scoped>


section {
    text-align: center;
    display: grid;
    gap: 7.5vh;
    max-width: 1500px;
    margin: 0 auto;
}
section .container {
    display: grid;
    place-items: center;
    gap: 5vw;
    grid-template-columns: repeat(3, 1fr);
    padding: 2vh 5vw;
}
section .container .element {
    width: 100%;
}

</style>