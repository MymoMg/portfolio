<script setup>

const props = defineProps({
    title: String
})

</script>


<template>
    <section>
        <div class="shapes">
            <span></span>
            <span></span>
        </div>
        <div class="content">
            <h2>{{ title }}</h2>
            <div class="container">
                <slot />
            </div>
        </div>
    </section>
</template>


<style scoped>


section {
    text-align: center;
    display: grid;
    gap: 7.5vh;
    margin: 0 auto;
}
section > img {
    width: 100%;
    height: 87%;
    position: absolute;
    transform: translate(-50%, -50%);
    top: 50%;
    left: 50%;
}
section .shapes {
    filter: blur(10px);
    position: absolute;
    inset: 0;
}
section .shapes span {
    background: linear-gradient(to right, 
        var(--secondary-accent-color-variant),
        var(--primary-accent-color-variant)  
    );
    position: absolute;
    z-index: -1;
    clip-path: polygon(100% 100%, 0% 100% , 0.00% 31.71%, 1.00% 31.61%, 2.00% 31.45%, 3.00% 31.22%, 4.00% 30.94%, 5.00% 30.60%, 6.00% 30.20%, 7.00% 29.75%, 8.00% 29.25%, 9.00% 28.70%, 10.00% 28.11%, 11.00% 27.48%, 12.00% 26.82%, 13.00% 26.12%, 14.00% 25.40%, 15.00% 24.66%, 16.00% 23.90%, 17.00% 23.13%, 18.00% 22.35%, 19.00% 21.57%, 20.00% 20.80%, 21.00% 20.03%, 22.00% 19.29%, 23.00% 18.56%, 24.00% 17.85%, 25.00% 17.18%, 26.00% 16.53%, 27.00% 15.93%, 28.00% 15.37%, 29.00% 14.85%, 30.00% 14.38%, 31.00% 13.97%, 32.00% 13.61%, 33.00% 13.31%, 34.00% 13.06%, 35.00% 12.88%, 36.00% 12.76%, 37.00% 12.70%, 38.00% 12.71%, 39.00% 12.78%, 40.00% 12.91%, 41.00% 13.11%, 42.00% 13.36%, 43.00% 13.68%, 44.00% 14.05%, 45.00% 14.48%, 46.00% 14.96%, 47.00% 15.48%, 48.00% 16.05%, 49.00% 16.67%, 50.00% 17.32%, 51.00% 18.00%, 52.00% 18.71%, 53.00% 19.44%, 54.00% 20.20%, 55.00% 20.96%, 56.00% 21.74%, 57.00% 22.51%, 58.00% 23.29%, 59.00% 24.06%, 60.00% 24.82%, 61.00% 25.55%, 62.00% 26.27%, 63.00% 26.96%, 64.00% 27.62%, 65.00% 28.24%, 66.00% 28.82%, 67.00% 29.36%, 68.00% 29.85%, 69.00% 30.29%, 70.00% 30.68%, 71.00% 31.01%, 72.00% 31.28%, 73.00% 31.49%, 74.00% 31.64%, 75.00% 31.72%, 76.00% 31.75%, 77.00% 31.70%, 78.00% 31.60%, 79.00% 31.43%, 80.00% 31.21%, 81.00% 30.92%, 82.00% 30.57%, 83.00% 30.17%, 84.00% 29.71%, 85.00% 29.21%, 86.00% 28.66%, 87.00% 28.06%, 88.00% 27.43%, 89.00% 26.76%, 90.00% 26.07%, 91.00% 25.34%, 92.00% 24.60%, 93.00% 23.84%, 94.00% 23.07%, 95.00% 22.29%, 96.00% 21.51%, 97.00% 20.74%, 98.00% 19.98%, 99.00% 19.23%, 100.00% 18.50%);
}

section .shapes span:first-of-type{
    inset: 10% 0 50% 0;
}
section .shapes span:last-of-type {
    inset: 50% 0 0% 0;
    background: linear-gradient(to right, 
        var(--primary-accent-color-variant),  
        var(--secondary-accent-color-variant)
    );
    transform: scale(-1) translateY(0.2px);
}

section > .content {
    padding: 5vh 0;
    margin: 10vh 0;
}
section .container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    max-width: 1400px;
    margin: 0 auto;
    gap: 5rem 8rem;
    grid-template-columns: repeat(3, 1fr);
    padding: 15vh 5vw;
}

@media screen and (max-width: 800px) {
    section .shapes {
        width: 200vw;
    }
}

</style>