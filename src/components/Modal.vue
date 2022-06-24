<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="projectModal">
            <h2 class="headerModal">{{ header }}</h2>
            <div class="project">
                <img @click="openProject" v-for="project in projects" :key="project" :src="project.img" :alt="project.title"> 
            </div>
        </div>
    </div>

    <div v-if="showProject1">
        <Project @close="openProject"/>
    </div>
</template>

<script>
import Project from './Project.vue'

export default {
    components: { Project },
    props: [ 'header', 'test' ],
    data() {
        return {
            projects: [
                { title: 'Project 1', img: require('../assets/img/photo.png') },
                { title: 'Project 2', img: require('../assets/img/photo.png') },
                { title: 'Project 3', img: require('../assets/img/photo.png') },
            ],
            showProject1: false,
        }
    },
    methods:{
        closeModal() {
            this.$emit('close')
        },
        openProject() {
            this.showProject1 = ! this.showProject1
        }
    }
}
</script>
