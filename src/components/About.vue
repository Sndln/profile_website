<template>
    <div class="backdrop" @click.self="closeAbout">
        <div class="projectModal">
            <h2 class="headerModal">{{ about }}</h2>
            <div class="projects">
                <p>{{ aboutMetext }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: [ 'about', 'test' ],
    aboutMetext: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptas saepe debitis quo minus veritatis, eum facilis atque. Maiores eveniet quisquam culpa, provident ad impedit. Dolor eum voluptatum veritatis qui illum?', 
    methods:{
        closeAbout() {
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