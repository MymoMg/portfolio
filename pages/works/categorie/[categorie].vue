<script setup>

import projects from '@/contents/projects.json'

const { categorie } = useRoute().params

const currentProject = projects.filter((project) => project.categorie && project.categorie === categorie);
const currentProjectData = currentProject[0] ? currentProject[0] : navigateTo("/");


</script>

<template>
	<main>
		<h1>{{categorie}}</h1>
	</main>
</template>

<style scoped>

main {
	padding-top: var(--header-height);
}

</style>