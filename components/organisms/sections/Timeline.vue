<script setup>

import Time from '~/components/molecules/Time.vue';

const props = defineProps({
    heading: String
})

</script>

<template>
    <section class="timeline">
        <h2 v-if="heading">{{ heading }}</h2>
        <div>
            <slot />
        </div>
    </section>
   
</template>
<style scoped>

.timeline {
  max-width: 1300px;
  margin: 0 auto;
  padding: 10vw;
}
.timeline > div {
    position: relative;
}
.timeline > div::after {
  content: '';
  position: absolute;
  width: 6px;
  background-color: var(--secondary-accent-color);
  box-shadow: 0 0 10px rgb(0, 0, 0, 0.15);
  top: 0;
  bottom: 0;
  left: 0;
  transform: translateX(-50%);
}

@media screen and (min-width: 600px) {
    .timeline > div::after {
        left: 50%;
    }
    .timeline h2 {
        text-align: center;
    }
}

</style>