<script setup>

const props = defineProps({
    right: Boolean,
    heading: String,
    desciption :String,
})

</script>

<template>
    <article :class="right ? 'right' : '' ">
        <div>
            <h3>{{ heading }}</h3>
            <p>{{ desciption }}</p>
        </div>
    </article>
</template>

<style scoped>

article {
  padding: 1rem 1.5rem;
  position: relative;
  width: 100%;
}

article::after {
    content: '';
    position: absolute;
    width: 1.5rem;
    aspect-ratio: 1/1;
    border-radius: 50%;
    background-color: var(--secondary-color);
    border: 2px solid var(--secondary-accent-color);
    box-shadow: 0 0 10px rgb(0, 0, 0, 0.15);
    top: 50%;
    z-index: 1;
    transform: translate(-50%,-50%);
    left: 0;
}

article > div {
    background-color: var(--secondary-color);
    padding: 1rem 1.5rem;
    border-radius: 15px;
    position: relative;
    box-shadow: 0 0 10px rgb(0, 0, 0, 0.15);
    border: 1px solid var(--secondary-accent-color-variant);
}

article > div::before {
  content: '';
  position: absolute;
  background-color: transparent;
  top: 50%;
  z-index: 1;
  border: medium solid ;
  border-width: 10px 0 10px 10px;
  border-color: transparent transparent transparent var(--secondary-accent-color-variant);
  left: 0;
  transform: translate(-100%, -50%) rotate(180deg);
}

article.right {
    margin-left: auto;
}


@media screen and (min-width: 600px) {
    article {
        width: 50%;
    }
    article:not(.right)::after {
        transform: translate(50%,-50%);
        right: 0;
        left: auto;
    }
    article:not(.right) > div::before {
        transform: translate(100%, -50%);
        right: 0;
        left: auto;
    }
}
</style>

