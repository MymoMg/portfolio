<script setup>

import CardTest from '~/components/molecules/CardTest.vue';
import Time from '~/components/molecules/Time.vue';

const dataCards = [
    {
        heading: "UI/UX",
        icon: "UI"
    },
    {
        heading: "Charte Graphique",
        icon: "Charte"
    },
    {
        heading: "Supports Visuels",
        icon: "Support"
    },
    {
        heading: "Photographie",
        icon: "Photo"
    },
    {
        heading: "Projets Alternance",
        icon: "Alternance"
    }
]

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
            <CardTest v-for="dataCard in dataCards"
                :heading="dataCard.heading"   
                :icon="dataCard.icon" 
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