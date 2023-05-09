<script setup>

import projects from '@/contents/projects.json'

const { id } = useRoute().params

const currentProject = projects.filter((project) => project.id && project.id === id);
const currentProjectData = currentProject[0] ? currentProject[0] : navigateTo("/");


</script>

<template>
	<main>
		<h1>{{ currentProjectData.id }}</h1>
		<p>{{  currentProjectData.description }}</p>
	</main>
</template>

<style scoped>

main {
	padding-top: var(--header-height);
}

</style>