<template>
    <div class="backdrop" @click.self="closeContact">
        <div class="projectModal">
            <h2 class="headerModal">{{ header2 }}</h2>
            
            <form @submit.prevent="submitForm">
                <label>Name</label>
                <input type="text" required v-model="name">

                <label for="">Lastname</label>
                <input type="text" required v-model="lastname">

                <label for="">Email</label>
                <input type="email" required v-model="email">

                <label for="">Message</label>
                <textarea name="message" id="message" cols="30" rows="5" v-model="message"></textarea>

                <button class="fbutton">Send message</button>
            </form>
        </div>
    </div>  
</template>

<script>
export default {
    props: [ 'header2' , 'test' ],
    data(){
        return {
            name: '',
            lastname: '',
            email: '',
            message:'Type here!'
        }
    },

    methods: {
        closeContact() {
            this.$emit('close')
        },
        submitForm(){
            console.log(this.name, this.lastname, this.email, this.message)
        }
    }
    }
</script>

<style scoped>
p {
    color: hotpink;
}

</style>