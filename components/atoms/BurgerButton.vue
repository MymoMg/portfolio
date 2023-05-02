<script setup>

const props = defineProps({
    cross: Boolean,
    clicked: Function
})

</script>

<template >
    <button @click="() => clicked && clicked()" :class="cross ? 'cross' : ''">
        <span></span>
        <span></span>
        <span></span>
    </button>
</template>

<style scoped>

button {
    height: 2.5rem;
    width: 2rem;
    display: grid;
    place-items: center;
    position: relative;
}

button > span {
    position: absolute;
    border-radius: 100vmax;
    width: 100%;
    height: 10%;
    background-color: var(--primary-color);
    transform: translateY(calc(300% * var(--i)));
    transition: transform .3s ease-in-out, opacity .2s ease-in-out;
}


button > span:first-child {
    --i: 1;
}

button > span:last-child {
    --i: -1;
}
button.cross > span {
    transform: rotate(calc(135deg * var(--i)));
}
button.cross > span:nth-child(2) {
    opacity: 0;
    transform: translateX(25%);
}

</style>