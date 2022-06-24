<template>
<div class="shadow">
  <div class="header">
    <div class="intro">
      <h1>{{ role }}</h1>
      <p>{{ intro }}</p>
      <!--<div class="skill">
        <img class="skills" v-for="skills in images" :key="skills" :src="skills.img" :alt="skills.title">
      </div>-->
    </div>
    <div class="box2">
      <img @click="toggleAbout" class="profPic" :src="profilePic" :alt="profilePic" />
      <h2 class="name">{{ name }}</h2>
    </div>
  </div>

  <!--<div class="gradient"></div>-->
  <div class="menu">
    <div class="projects">
      <button class="mbutton" @click="toggleModal">Projects</button>
    </div>
    <div class="resume">
      <button class="mbutton" @click="toggleResume">Resume</button>
    </div>
    <div class="contact">
      <button class="mbutton" @click="toggleContact">Contact</button>
    </div>
  </div>
  <div v-if="showAbout">
    <About :about="about" :test="test" @close="toggleAbout"/>
  </div>
  <div v-if="showModal">
    <Modal :header="header" :test="test" @close="toggleModal"/>
  </div>
  <div v-if="showResume">
    <Resume :header1="header1" :test="test" @close="toggleResume"/>
  </div>
  <div v-if="showContact">
    <Contact :header2="header2" :test="test" @close="toggleContact"/>
  </div>
  </div>

</template>

<script>
import Modal from './components/Modal.vue'
import Resume from './components/Resume.vue'
import Contact from './components/Contact.vue'
import About from './components/About.vue'

export default {
  name: 'App',
  components: { Modal , Resume , Contact , About },

  data() {
    return {
      role: 'Front-end Developer / UX Desinger',
      intro: 'Hi Welcome op mijn webiste. Hier vertel ik wat over mezelf en een paar projecten waar aan ik heb gewerkt. Wil je meer weten? neem dan contact met mij op.',
      profilePic: require('./assets/img/sjmirza.jpeg'),
      name: 'Sandeleen Mirza',
      images: [
        { title: 'html', img: require('./assets/img/htmll.png') },
        { title: 'css', img: require('./assets/img/cssl.png') },
        { title: 'javascript', img: require('./assets/img/js.png') },
      ],
      showModal: false,
      showResume: false,
      showContact: false,
      showAbout: false,
      header: 'Projects',
      header1: 'Resume',
      header2: 'Contact',
      about: 'About me!',
      test: 'dit is een test',
    }
    
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleResume(){
      this.showResume = !this.showResume
    },
    toggleContact(){
      this.showContact = !this.showContact
    },
    toggleAbout(){
      this.showAbout = !this.showAbout
    }
  }
}


</script>