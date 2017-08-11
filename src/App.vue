<template>
  <div id="app">
     <landing></landing>
     <!--<navbar></navbar>-->
     <about></about>
     <skills :showSkills="showSkills"></skills>
     <experience></experience>
  </div>
</template>

<script>
import Landing from './components/Landing.vue';
import About from'./components/About.vue';
import Navbar from './components/Navbar.vue';
import Skills from './components/Skills.vue';
import Experience from './components/Experience.vue';
export default {
    name: 'app',
    data () {
          return {
              showSkills: false
          }
    },
    components: {
        'landing': Landing,
        'about': About,
        'navbar': Navbar,
        'skills': Skills,
        'experience': Experience
    },
    methods:{
        checkScroll(){
            let scrollPosition = document.getElementById('skills');
            let top = scrollPosition.getBoundingClientRect().top;
            if (top <= 400){
                this.showSkills = true;
            }
        }
    },
    created: function(){
        window.addEventListener('scroll', this.checkScroll);
    }
}
</script>

<style lang="scss">
    * {
        color: #454545;
        font-family: 'Quattrocento Sans', sans-serif;
    }
    .headings {
        font-family: 'Oswald', sans-serif;
        text-transform: uppercase;
        letter-spacing: 1vw;
        font-size: 4em;
    }
    .sub-headings {
        font-family: 'Oswald', sans-serif;
        text-transform: uppercase;
        font-size: 2em;
        letter-spacing: 0.25vw;
    }
</style>
