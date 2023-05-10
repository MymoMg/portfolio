<script setup>

import projects from '@/contents/projects.json'

const { project_id, category } = useRoute().params

const currentProject = projects.filter((project) => 
	project.categorie === category && project.id === project_id
);
const currentProjectData = currentProject[0] ? currentProject[0] : navigateTo("/");


</script>

<template>
	<main>
		{{ $route.href.split("/") }}
		<h1>{{ currentProjectData.id.split("_").join(" ") }}</h1>
		<p>{{  currentProjectData.description }}</p>
	</main>
</template>

<style scoped>

main {
	padding-top: var(--header-height);
}

</style>