<template>
  <div id="app">
     <landing></landing>
     <!--<navbar :class="{ isSticky: stickyNav }"></navbar>-->
     <about></about>
     <skills></skills>
     <!--<experience></experience>-->
     <bottom></bottom>
  </div>
</template>

<script>
import Landing from './components/Landing.vue';
import About from'./components/About.vue';
import Navbar from './components/Navbar.vue';
import Skills from './components/Skills.vue';
import Experience from './components/Experience.vue';
import Footer from './components/Footer.vue';
export default {
    name: 'app',
    data () {
          return {
              showSkills: false,
              stickyNav: false
          }
    },
    components: {
        'landing': Landing,
        'about': About,
        'navbar': Navbar,
        'skills': Skills,
        'experience': Experience,
        'bottom': Footer
    },
    methods:{
        checkScroll(){
            let scrollPosition = document.getElementById('navbar');
            let top = scrollPosition.getBoundingClientRect().top;
            console.log(top);
            if (top <= 0){
                this.stickyNav = true;
            }
            else if(top >= 0) {
                this.stickyNav = false;
            }
        }
    },
    created: function(){
//        window.addEventListener('scroll', this.checkScroll);
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
    .isSticky {
        position: fixed;
        top: 0;
        background-color: rgba(0,0,0,0.4);
    }
</style>
