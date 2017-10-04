<template>
  <div id="app">
     <navbar :showNav="showNav"></navbar>
     <landing></landing>
     <about></about>
     <skills></skills>
     <experience :expScrolledTo="expScrolledTo"></experience>
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
              expScrolledTo: false,
              showNav: false
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
            const experienceSection = document.getElementById('Experience');
            const topOfExpSection = experienceSection.getBoundingClientRect().top;
            const windowHeight = Math.max(document.documentElement.clientHeight);
            const halfViewHeight= windowHeight / 2;

            if (topOfExpSection <= 450){
                this.expScrolledTo = true;
            }

            if (document.documentElement.scrollTop || window.pageYOffset > halfViewHeight) {
                this.showNav = true;
            } else {
                this.showNav = false;
            }
        },

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
        font-family: 'Teko', sans-serif;
        text-transform: uppercase;
        letter-spacing: 0.075em;
        font-size: 4.5em;
    }
    .sub-headings {
        font-family: 'Teko', sans-serif;
        text-transform: uppercase;
        font-size: 2em;
        letter-spacing: 0.25vw;
    }


</style>
