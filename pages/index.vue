<script setup>

import CategoryCard from '~/components/molecules/CategoryCard.vue';
import Time from '~/components/molecules/Time.vue';
import projects from '@/contents/projects.json'

const category_names_per_project = projects.map((el) => el.categorie)
const category_names = category_names_per_project.filter((x, i) =>
    category_names_per_project.indexOf(x) === i
)  

const dataTimes = [
    {
        title:"2023",
        desciption:"Lorem ipsum dolor, sit amet consectetur adipisicing elit. Culpa, pariatur. Suscipit assumenda minima sapiente, debitis facilis libero nobis animi fugit necessitatibus aperiam voluptate sit officiis, numquam odit quibusdam architecto tempora!",
    },
    {
        title:"2024",
        desciption:"Lorem ipsum dolor, sit amet consectetur adipisicing elit. Culpa, pariatur. Suscipit assumenda minima sapiente, debitis facilis libero nobis animi fugit necessitatibus aperiam voluptate sit officiis, numquam odit quibusdam architecto tempora!",
    },
    {
        title:"2023",
        desciption:"Lorem ipsum dolor, sit amet consectetur adipisicing elit. Culpa, pariatur. Suscipit assumenda minima sapiente, debitis facilis libero nobis animi fugit necessitatibus aperiam voluptate sit officiis, numquam odit quibusdam architecto tempora!",
    },
    {
        title:"2023",
        desciption:"Lorem ipsum dolor, sit amet consectetur adipisicing elit. Culpa, pariatur. Suscipit assumenda minima sapiente, debitis facilis libero nobis animi fugit necessitatibus aperiam voluptate sit officiis, numquam odit quibusdam architecto tempora!",
    },
    {
        title:"2024",
        desciption:"Lorem ipsum dolor, sit amet consectetur adipisicing elit. Culpa, pariatur. Suscipit assumenda minima sapiente, debitis facilis libero nobis animi fugit necessitatibus aperiam voluptate sit officiis, numquam odit quibusdam architecto tempora!",
    },
    {
        title:"2023",
        desciption:"Lorem ipsum dolor, sit amet consectetur adipisicing elit. Culpa, pariatur. Suscipit assumenda minima sapiente, debitis facilis libero nobis animi fugit necessitatibus aperiam voluptate sit officiis, numquam odit quibusdam architecto tempora!",
    },
    {
        title:"2023",
        desciption:"Lorem ipsum dolor, sit amet consectetur adipisicing elit. Culpa, pariatur. Suscipit assumenda minima sapiente, debitis facilis libero nobis animi fugit necessitatibus aperiam voluptate sit officiis, numquam odit quibusdam architecto tempora!",
    }
]

</script>

<template>
    <main>
        <Hero 
            heading="Bonjour, je suis Meriem Mguil"
            catchphrase="Etudiante en 2ème année de BUT MMI alternance graphisme-communication, je recherche une nouvelle opportunité d'alternance pour l'année 2023/2024 afin d'élargir mes horizons et d'acquérir de nouvelles expériences."
        />
        <Wrapper title="Mes Projets">
            <CategoryCard v-for="dataCard in category_names"
                :category_name="dataCard"
            />
        </Wrapper>
        <Timeline>
            <Time v-for="(dataTime, index) in dataTimes"
                :heading="dataTime.title" 
                :desciption="dataTime.desciption"
                :right="index % 2 === 0 ? false : true"
            />
        </Timeline>
    </main>
</template>