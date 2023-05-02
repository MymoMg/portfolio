<template>
    <header >
        <NuxtLink to="/" class="logo">
            <img src="https://loremflickr.com/320/240?random=1"/>
        </NuxtLink>
        <nav>
            <BurgerButton :clicked="handleClick" :cross="opened"/>
            <ul :class="opened ? 'opened' : ''">
                <li><NuxtLink to="">test</NuxtLink></li>
                <li><NuxtLink to="">test</NuxtLink></li>
                <li><NuxtLink to="">test</NuxtLink></li>
                <li><NuxtLink to="">test</NuxtLink></li>
                <li><NuxtLink to="">test</NuxtLink></li>
            </ul>
        </nav>
    </header>
</template>

<script>
import BurgerButton from '../atoms/BurgerButton.vue';

export default{
    components: {
        BurgerButton
    },
    data() {
        return {
            opened: false
        }
    },
    methods: {
        handleClick() {
            this.opened = !this.opened
        }
    }
}
</script>


<style scoped> 

header {
    position: fixed;
    top: 0;
    left: 0;
    height: var(--header-height);
    width: 100%;
    background-color: var(--secondary-color);
    color: var(--primary-color);
    padding: 1vh 3vw;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0 0 10px rgb(0,0,0, 0.3);
    z-index: 1000;
}
header :is(.logo, .logo img) {
    height: 100%;
}

header nav ul {
    position: fixed;
    top: var(--header-height);
    left: 115%;
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    flex-direction: column;
    width: 100%;
    height: calc(100vh - var(--header-height));
    background-color: var(--secondary-color);
    box-shadow: inset 0 0 10px rgb(0,0,0, 0.3);
    transition: left .4s ease-in-out;
    z-index: 900;
}

header nav ul.opened {
    left: 0
}



</style>