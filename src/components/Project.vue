<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="projectModal">
            <h2 class="headerModal">{{  }}</h2>
            <div class="project">
                <h1>{{ header }}</h1> 
                <p>{{ text }}</p>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    data(){
        return{
            header: 'Project 1',
            text: 'lorem ipsum text',
        }
    },
    methods:{
        closeModal(){
            this.$emit('close')
        }
    }
}
</script>

<style scoped>
p {
    color: hotpink;
}
</style>