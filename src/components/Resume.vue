<template>
    <div class="backdrop" @click.self="closeResume">
        <div class="projectModal">
            <h2 class="headerModal">{{ header1 }}</h2>
            <div class="cv">
            <img class="onePager" src="../assets/img/resume.jpg" alt="Resume">
            </div>
            <div class="print">
            <img onclick="window.print()" src="../assets/img/printer.png" alt="Print">
            </div>
        </div>
    </div>  
</template>

<script>
export default {
    resume: require('../assets/img/resume.jpg'),
    props: [ 'header1', 'test' ],
    methods: {
        closeResume() {
            this.$emit('close')
        }
    }
    }
</script>

<style scoped>
p {
    color: hotpink;
}

.onePager {
    width: 90%;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0;
    margin: 0;
    box-shadow: -5px 5px 5px rgba(0, 0, 0, 0.3);
}

.print {
    opacity: 50%;
    display: flex;
    justify-content: center;
    padding: 0;
    margin: 0;
}

.print img {
    width: 25px;
    padding: 0;
    margin: 15px 0 0 0;
}


</style>