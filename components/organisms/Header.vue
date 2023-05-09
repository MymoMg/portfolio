<template>
    <header :class="`${scrolled ? 'scrolled' : ''} ${hero ? 'hero' : ''}`">
        <div>
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
                </ul>
            </nav>
        </div>
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
            opened: false,
            scrolled: false,
            hero: null,
        }
    },
    mounted() {
        window.addEventListener('scroll', () => this.handleScroll())
        this.hero = this.$route.fullPath === '/' ? true : false
    },
    methods: {
        handleClick() {
            this.opened = !this.opened
        },
        handleScroll() {
            this.scrolled = window.scrollY > 0 ? true : false
        }
    }
}
</script>


<style scoped> 

header {
    background-color: transparent;
    position: fixed;
    top: 0;
    left: 0;
    height: var(--header-height);
    width: 100%;
    color: var(--primary-color);
    padding: 1vh 3vw;
    z-index: 1300;
    transition: background-color .5s cubic-bezier(0.215, 0.610, 0.355, 1), box-shadow .5s cubic-bezier(0.215, 0.610, 0.355, 1),;
}

header.scrolled {
    backdrop-filter: blur(10px);
    background-color: var(--secondary-color-second-variant);
    box-shadow: 0 0 10px rgb(0,0,0, 0.3);
}

header > div {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 100%;
    margin: 0 auto;
    max-width: 1000px;
}
header :is(.logo, .logo img) {
    height: 100%;
}

header nav ul {
    position: fixed;
    top: var(--header-height);
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    flex-direction: column;
    left: 0;
    width: 100%;
    height: calc(100vh - var(--header-height));
    background-color: var(--secondary-accent-color-variant);
    box-shadow: inset 0 0 10px rgb(0,0,0, 0.3);
    transform: translateX(115%);
    font-size: 1.2rem;
    text-transform: capitalize;
    font-family: sans-serif;
    letter-spacing: 2px;
    transition: transform .4s ease-in-out;
    z-index: 900;
}

header nav ul.opened {
    transform: translateX(0);
}

@media screen and (min-width : 800px) {
    header nav > :first-child {
        display: none;
    }
    header nav ul {
        position: initial;
        flex-direction: row;
        height: auto;
        box-shadow: none;
        gap: 2.5rem; 
        background-color: transparent;
        transform: initial;
    }  
    header.hero nav ul {
        color: white;
        mix-blend-mode: difference;
    }
}



</style>