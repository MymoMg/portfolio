<script setup>

import Icon from '../atoms/Icon.vue';

const props = defineProps({
  heading: String,
  icon: String,
})

</script>

<template>
  <article>
    <NuxtLink to="/" class="cardLink">
        <div>
          <Icon :name="icon" class="icon"/>
          <h3>{{ heading }}</h3>
        </div>
    </NuxtLink>
  </article>
</template>

<style scoped>
    
@property --gradient-angle {
  syntax: "<angle>";
  initial-value: 0deg;
  inherits: false;
}

.cardLink {
  display: grid;
  position: relative;
  background-color: var(--secondary-color);
  padding: 0.5rem;
  border-radius: 20px;
  width: 215px;
  transform: scale(1);
  box-shadow: 0 0 15px rgba(0,0,0, 0.55);
  transition: transform .3s ease-in-out, box-shadow .4s;
}
.cardLink .icon {

  height: 5.5rem;
  margin: 0 auto;
  margin-bottom: 2rem;
  transition: transform .5s;
}

.cardLink h3 {
  height: 4.5rem; 
  display: grid;
  padding: 0 5%;
  place-items: center;
}

.cardLink > div {
    display: grid;
    place-items: center;
    position: relative;
    padding: 3.5rem 1rem 2rem 1rem;     
    background-color: inherit;
    border-radius: inherit;
}
.cardLink > div::before,
.cardLink > div::after{
  content: "";
  position: absolute;
  inset: -1px;
  z-index: -1;
  background: conic-gradient(from var(--gradient-angle),
    var(--primary-accent-color),
    var(--secondary-accent-color),
    var(--primary-accent-color)
  );
  border-radius: inherit;
  animation: rotation 2s linear infinite;
}

.cardLink > div::after {
  filter: blur(2px);
}
.cardLink:is(:hover, :focus) {
  transform: scale(1.05);
}
.cardLink:is(:hover, :focus) .icon {
  transform: scaleY(1.05);
}


@keyframes rotation {
  0% {
    --gradient-angle: 0deg;
  }
  100% {
    --gradient-angle: 360deg;
  }
}

</style>