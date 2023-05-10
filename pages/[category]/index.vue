<script setup>
import ProjectCard from '~/components/molecules/ProjectCard.vue';
import projects from '@/contents/projects.json'

const { category } = useRoute().params

const currentProjectDatas = projects.filter((project) => project.categorie && project.categorie === category);
currentProjectDatas[0] ? '' : navigateTo("/");

</script>

<template>
	<main>
		<h1>{{category.split("_").join(" ")}}</h1>
		<div>
			<ProjectCard v-for="(projectCardData, index) in currentProjectDatas"
				:key="index" 
				:project_name="projectCardData.id"
			/>
		</div>
	</main>
</template>

<style scoped>

main {
	padding-top: var(--header-height);
}

</style>