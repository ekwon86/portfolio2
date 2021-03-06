<template>
    <div id="Portfolio">
        <div class="portfolio-content">
          <p class="headings portfolio-heading">Portfolio</p>
          <div class="project-container">
            <div class="indiv-project-subcontainers" v-for="(project, index) in projects">
                <div class="indiv-project-img-holder">
                    <div class="indiv-projects-overlay" v-on:mouseover="showProjectContents(index)" v-on:mouseleave="hideProjectContents(index)">
                        <div class="project-contents">
                            <transition name="slide-fade-top">
                                <div v-if="project.showContents" class="project-contents-top">
                                    <h3 class="project-name">{{ project.name }}</h3>
                                </div>
                            </transition>
                            <transition name="slide-fade-bottom">
                                <div v-if="project.showContents" class="project-contents-bottom">
                                    <a :href="project.github" target="_blank" v-if="project.github">
                                        <i class="fa fa-github fa-2x project-icons" aria-hidden="true"></i>
                                    </a>
                                    <i class="fa fa-info-circle fa-2x project-icons" aria-hidden="true" v-on:click="displayModal(index)"></i>
                                    <a :href="project.url" target="_blank" v-if="project.url">
                                        <i class="fa fa-rocket fa-2x project-icons" aria-hidden="true"></i>
                                    </a>
                                </div>
                            </transition>
                        </div>
                    </div>
                    <div class="indiv-projects-img" :id="project.id"></div>
                </div>
            </div>
          </div>
        </div>
        <!-- PROJECT MODAL START -->
        <transition name="fade">
            <div id="project-modal-overlay" v-if="showProjectModal">
                <div class="project-info">
                    <div class="project-info-picture-holder" v-bind:style="{ 'background-image': 'url(/dist/' + modal.projectPicPath + '.jpg)' }">
                        <i class="fa fa-times-circle exit-icon" aria-hidden="true" v-on:click="closeModal()"></i>
                    </div>
                    <div class="project-info-info-holder">
                        <div class="project-info-name-and-tech-holder">
                            <div class="project-info-name-container">
                                <h3 class="project-info-modal-name">
                                  {{ modal.projectName }}
                                  <img src="../assets/lfz.png" alt="lfz" class="lfz-logo" v-if="modal.isLFZ"/>
                                </h3>
                            </div>
                            <div class="project-info-tech-container">
                                <div class="project-info-tech-icon-container">
                                     <span v-for="skill in modal.projectTechsUsed">
                                        <i :class="'skill-icons devicon-' + skill.icon + ' colored devicons'" data-toggle="tooltip" :title="skill.lang"></i>
                                    </span>
                                </div>
                            </div>
                        </div>
                        <div class="project-info-desc-container">
                            <p class="project-description">{{ modal.projectDescription }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </transition>
        <!-- PROJECT MODAL END -->
    </div>
</template>

<script>
export default {
  data() {
    return {
      showProjectModal: false,
      modal: {
        projectName: '',
        projectImgPath: '',
        projectTechsUsed: [],
        projectPicPath: '',
        projectDescription: '',
        isLFZ: false
      },
      projects: [
        {
          name: 'Dev Connector',
          id: 'devconnector',
          github: 'https://github.com/ekwon86/devconnector',
          url: 'https://shielded-wave-20125.herokuapp.com',
          desc:
            'This is an application that I built using the MERN (MongoDB, Express, React, NodeJS) Stack. This full-stack application is able to register new users and authenticate existing users with the use of protected routes.',
          isLFZ: false,
          techsUsed: [
            { lang: 'MongoDB', icon: 'mongodb-plain' },
            { lang: 'Express', icon: 'express-original colored' },
            { lang: 'React', icon: 'react-original colored' },
            { lang: 'NodeJS', icon: 'nodejs-plain colored' },
            { lang: 'Heroku', icon: 'heroku-original colored' },
            { lang: 'Bootstrap', icon: 'bootstrap-plain colored' }
          ],
          showContents: false
        },
        {
          name: 'Genkiyaki Website',
          id: 'genkiyaki',
          github: 'https://github.com/ekwon86/genkiyaki',
          url: 'http://www.houseofgenkiyaki.com/',
          desc:
            'This is a custom website for a client that I built primarily using the Angular 4 framework. I utilized the Angular CLI to perform a variety of functions such as creating components and services, running a development environment, and bundling the application for deployment. Lastly, I utilized Heroku and the Heroku CLI to deploy the application.',
          isLFZ: false,
          techsUsed: [
            { lang: 'Angular', icon: 'angularjs-plain' },
            { lang: 'Javascript', icon: 'javascript-plain colored' },
            { lang: 'Heroku', icon: 'heroku-original colored' },
            { lang: 'Bootstrap', icon: 'bootstrap-plain colored' },
            { lang: 'HTML', icon: 'html5-plain' },
            { lang: 'CSS', icon: 'css3-plain colored' }
          ],
          showContents: false
        },
        {
          name: 'Web Portfolio',
          id: 'portfolio',
          github: 'https://github.com/ekwon86/portfolio2',
          url: '',
          desc:
            'My web portolio was created from scratch using the VueJS library. I utilized the Vue CLI to develop this portfolio on a local development environment and also to bundle and deploy it once finished.',
          isLFZ: false,
          techsUsed: [
            { lang: 'Vue', icon: 'vuejs-plain colored' },
            { lang: 'Javascript', icon: 'javascript-plain colored' },
            { lang: 'Sass', icon: 'sass-original colored' },
            { lang: 'Bootstrap', icon: 'bootstrap-plain colored' },
            { lang: 'HTML', icon: 'html5-plain' },
            { lang: 'CSS', icon: 'css3-plain colored' }
          ],
          showContents: false
        },
        {
          name: 'Conference Page',
          id: 'wordpress',
          github: '',
          url: 'http://www.laserapp.com/conference2017/',
          desc:
            'This conference site was created primarily using Wordpress and a variety of plugins. I also embedded snippets of raw HTML, CSS, and Javascript to give the site further styling, structure, and functionality.',
          isLFZ: false,
          techsUsed: [
            { lang: 'Wordpress', icon: 'wordpress-plain colored' },
            { lang: 'Javascript', icon: 'javascript-plain colored' },
            { lang: 'Bootstrap', icon: 'bootstrap-plain colored' },
            { lang: 'HTML', icon: 'html5-plain' },
            { lang: 'CSS', icon: 'css3-plain colored' }
          ],
          showContents: false
        },
        {
          name: 'Conference Schedule',
          id: 'conferenceschedule',
          github: 'https://github.com/ekwon86/conferenceschedule',
          url: 'http://www.eugenekwon.com/projects/conferenceschedule/',
          desc:
            'This is an application that was developed utilizing the VueJS library. A http request is made to the Fieldbook and Wunderground APIs to retrieve the conference schedule and weather forecast respectively. Said information is then displayed on a large screen to conference attendees.',
          isLFZ: false,
          techsUsed: [
            { lang: 'Vue', icon: 'vuejs-plain colored' },
            { lang: 'Javascript', icon: 'javascript-plain colored' },
            { lang: 'Bootstrap', icon: 'bootstrap-plain colored' },
            { lang: 'HTML', icon: 'html5-plain' },
            { lang: 'CSS', icon: 'css3-plain colored' }
          ],
          showContents: false
        },
        {
          name: "What's for Lunch?",
          id: 'whatsforlunch',
          github: 'https://github.com/ekwon86/whatsforlunch',
          url: 'http://www.eugenekwon.com/projects/whatsforlunch',
          desc:
            'This is an application that I developed with several other developers while attending the LearningFuze programming bootcamp program. I assumed the role of a Front-End Developer and was responsible for the layout, design, and animations. The application makes an AJAX call to the Foursquare API and retrieves all restaurants within a 5 mile radius of the user.',
          isLFZ: true,
          techsUsed: [
            { lang: 'Javascript', icon: 'javascript-plain colored' },
            { lang: 'jQuery', icon: 'jquery-plain colored' },
            { lang: 'Bootstrap', icon: 'bootstrap-plain colored' },
            { lang: 'HTML', icon: 'html5-plain' },
            { lang: 'CSS', icon: 'css3-plain colored' }
          ],
          showContents: false
        },
        {
          name: 'Tic-Tac-Toe',
          id: 'tictactoe',
          github: 'https://github.com/ekwon86/tictactoe',
          url: 'http://www.eugenekwon.com/projects/tictactoe',
          desc:
            'This is an application that I developed in tandem with two other developers while attending the LearningFuze programming bootcamp program. I assumed the role of a Front-End Developer and handled most of the design and layout of the game, as well as contributing to various auxiliary functions required to play the game.',
          isLFZ: true,
          techsUsed: [
            { lang: 'Javascript', icon: 'javascript-plain colored' },
            { lang: 'jQuery', icon: 'jquery-plain colored' },
            { lang: 'Bootstrap', icon: 'bootstrap-plain colored' },
            { lang: 'HTML', icon: 'html5-plain' },
            { lang: 'CSS', icon: 'css3-plain colored' }
          ],
          showContents: false
        },
        {
          name: 'Calculator',
          id: 'calculator',
          github: 'https://github.com/ekwon86/calculator',
          url: 'http://www.eugenekwon.com/projects/calculator',
          desc:
            'This is an application that I developed independently while attending the LearningFuze programming bootcamp program primarily utilizing Javascript and jQuery to handle the calculations.',
          isLFZ: true,
          techsUsed: [
            { lang: 'Javascript', icon: 'javascript-plain colored' },
            { lang: 'jQuery', icon: 'jquery-plain colored' },
            { lang: 'Bootstrap', icon: 'bootstrap-plain colored' },
            { lang: 'HTML', icon: 'html5-plain' },
            { lang: 'CSS', icon: 'css3-plain colored' }
          ],
          showContents: false
        },
        {
          name: 'Mega Match Man',
          id: 'megamatchman',
          url: 'http://www.eugenekwon.com/projects/megamatchman',
          github: 'https://github.com/ekwon86/mega_match_man',
          desc:
            'This is an application that I developed independently while attending the LearningFuze programming bootcamp program primarily utilizing Javascript to handle the game logic.',
          isLFZ: true,
          techsUsed: [
            { lang: 'Javascript', icon: 'javascript-plain colored' },
            { lang: 'jQuery', icon: 'jquery-plain colored' },
            { lang: 'Bootstrap', icon: 'bootstrap-plain colored' },
            { lang: 'HTML', icon: 'html5-plain' },
            { lang: 'CSS', icon: 'css3-plain colored' }
          ],
          showContents: false
        }
      ]
    };
  },
  methods: {
    showProjectContents: function(index) {
      this.projects[index].showContents = true;
    },
    hideProjectContents: function(index) {
      this.projects[index].showContents = false;
    },
    displayModal(index) {
      this.showProjectModal = true;
      this.modal.projectName = this.projects[index].name;
      this.modal.projectTechsUsed = this.projects[index].techsUsed;
      this.modal.projectPicPath = this.projects[index].id;
      this.modal.projectDescription = this.projects[index].desc;
      this.modal.isLFZ = this.projects[index].isLFZ;
    },
    closeModal() {
      this.showProjectModal = false;
      this.modal.projectName = '';
      this.modal.projectTechsUsed = [];
      this.modal.projectPicPath = '';
      this.modal.projectDescription = '';
      this.modal.isLFZ = false;
    }
  }
};
</script>

<style lang="scss">
#Portfolio {
  height: 1100px;
  width: 100vw;
  position: relative;
  background-color: white;
  padding: 5% 15%;
  .portfolio-content {
    position: relative;
    top: 50%;
    width: 100%;
    transform: translateY(-50%);
    height: 100%;
    .portfolio-heading {
      border-bottom: 1px solid rgba(0, 0, 0, 0.1);
    }
  }
}
.project-container {
  min-height: 250px;
  font-size: 0;
  height: auto;
  vertical-align: top;
  border: 1px solid rgba(0, 0, 0, 0.075);
}
.indiv-project-subcontainers {
  padding: 10px;
  width: 33.33333%;
  display: inline-block;
  height: 250px;
  #devconnector {
    background: url(../assets/devconnector.jpg);
  }
  #megamatchman {
    background: url(../assets/megamatchman.jpg);
  }
  #calculator {
    background: url(../assets/calculator.jpg);
  }
  #tictactoe {
    background: url(../assets/tictactoe.jpg);
  }
  #genkiyaki {
    background: url(../assets/genkiyaki.jpg);
  }
  #portfolio {
    background: url(../assets/portfolio.jpg);
  }
  #wordpress {
    background: url('../assets/wordpress.jpg');
  }
  #whatsforlunch {
    background: url('../assets/whatsforlunch.jpg');
  }
  #conferenceschedule {
    background: url('../assets/conferenceschedule.jpg');
  }
}
.indiv-project-img-holder {
  height: 100%;
  width: 100%;
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16), 0 3px 6px rgba(0, 0, 0, 0.23);
  position: relative;
  overflow: hidden;
}
.indiv-projects-overlay {
  height: 100%;
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 2;
  background-color: rgba(0, 0, 0, 0.1);
  -moz-transition: all 0.3s ease;
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease;
  text-align: center;
}
.project-name {
  color: White;
  text-transform: uppercase;
  margin-bottom: 15px;
  letter-spacing: 3px;
}
.project-icons {
  z-index: 999;
  font-size: 30px;
  transition: 0.2s;
  color: white;
  margin: 0 15px;
  &:hover {
    cursor: pointer;
    color: #36beeb;
  }
}
.project-contents {
  position: relative;
  top: 50%;
  transform: translateY(-50%);
}
.indiv-projects-img {
  width: 100%;
  height: 100%;
  background-size: 100% 100% !important;
  background-position: center !important;
}
.indiv-projects-overlay:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

/*MODAL*/
#project-modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
  text-align: center;
  z-index: 999999999999;
  background-color: rgba(0, 0, 0, 0.6);
}
.project-info {
  height: 800px;
  width: 1200px;
  border: transparent;
  background-color: white;
  border-radius: 3px;
  overflow: hidden;
  position: relative;
  top: 50%;
  margin: auto;
  transform: translate(0, -50%);
}
.project-info-picture-holder {
  position: relative;
  width: 100%;
  height: 60%;
  text-align: right;
  padding: 25px 35px;
  background-size: cover;
  background-position: center center;
  .exit-icon {
    font-size: 80px;
    color: white;
    transition: 0.1s;
    &:hover {
      cursor: pointer;
      color: #ff4444;
    }
    &:active {
      color: #cc0000;
    }
  }
}
.project-info-desc-container {
  text-align: left;
  .project-description {
    font-size: 20px;
    color: #444444;
    text-align: justify;
  }
}

.project-info-info-holder {
  height: 40%;
  padding: 15px 30px;
  position: relative;
  .project-info-name-and-tech-holder {
    height: 25%;
    width: 100%;
    font-size: 0;
    position: relative;
    margin-bottom: 15px;
    border-bottom: 1px solid rgba(0, 0, 0, 0.3);
    .project-info-name-container {
      width: 50%;
      height: 100%;
      vertical-align: top;
      display: inline-block;
      text-align: left;
      position: relative;
      .project-info-modal-name {
        font-size: 50px;
        color: #444444;
        position: relative;
        top: 50%;
        transform: translateY(-50%);
        font-family: 'Teko', sans-serif;
        letter-spacing: 3px;
      }
    }
    .project-info-tech-container {
      width: 50%;
      vertical-align: top;
      height: 100%;
      display: inline-block;
      .project-info-tech-icon-container {
        position: relative;
        top: 50%;
        transform: translateY(-50%);
        text-align: right;
      }
      .skill-icons {
        font-size: 35px;
        margin-left: 15px;
      }
    }
  }
}

.lfz-logo {
  width: 200px;
  margin-left: 20px;
}

/*TRANSITIONS*/
.slide-fade-top-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-top-leave-active {
  transition: all 0.3s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-top-enter, .slide-fade-top-leave-to
        /* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateY(-25px);
  opacity: 0;
}
.slide-fade-bottom-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-bottom-leave-active {
  transition: all 0.3s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-bottom-enter, .slide-fade-bottom-leave-to
        /* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateY(25px);
  opacity: 0;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

/*MOBILE VIEW - PORTRAIT*/
@media (min-width: 320px) and (max-width: 480px) {
  #Portfolio {
    padding: 5% 10%;
    height: 1400px;
  }
  .indiv-project-subcontainers {
    width: 100%;
    height: 150px;
    padding: 5px;
  }
  .project-name {
    font-size: 1rem;
  }
  .project-icons {
    font-size: 25px;
  }
  .project-info {
    width: 100vw;
    height: 100vh;
  }
  .project-info-picture-holder {
    height: 40%;
    padding: 10px;
  }
  .project-info-info-holder {
    height: 60%;
    padding: 15px 10px;
  }
  .exit-icon {
    font-size: 50px !important;
  }
  .project-info-modal-name {
    font-size: 30px !important;
  }
  .skill-icons {
    font-size: 24px !important;
    margin-left: 8px !important;
  }
  .project-info-desc-container .project-description {
    font-size: 14px;
  }
}

/*MOBILE VIEW - LANDSCAPE*/
@media (min-width: 481px) and (max-width: 800px) {
  #Portfolio {
    padding: 5% 10%;
    height: 775px;
  }
  .indiv-project-subcontainers {
    width: 50%;
    height: 150px;
    padding: 5px;
  }
  .project-name {
    font-size: 1rem;
  }
  .project-icons {
    font-size: 25px;
  }
  .project-info {
    width: 100vw;
    height: 100vh;
  }
  .project-info-picture-holder {
    height: 40%;
    padding: 10px;
  }
  .project-info-info-holder {
    height: 60%;
    padding: 15px 10px;
  }
  .exit-icon {
    font-size: 50px !important;
  }
  .project-info-modal-name {
    font-size: 30px !important;
  }
  .skill-icons {
    font-size: 24px !important;
    margin-left: 8px !important;
  }
  .project-info-desc-container .project-description {
    font-size: 14px;
  }
}

/*LAPTOPS*/
@media (min-width: 1025px) and (max-width: 1280px) {
  #Portfolio {
    padding: 5% 10%;
    height: 900px;
  }

  .indiv-project-subcontainers {
    height: 200px;
  }
  .project-name {
    font-size: 1.25rem;
  }
  .project-info {
    width: 85vw;
    height: 85vh;
  }
  .project-info-picture-holder {
    height: 40%;
    padding-top: 10px;
  }
  .project-info-info-holder {
    height: 60%;
  }
  .lfz-logo {
    width: 20px;
  }
  .exit-icon {
    font-size: 65px !important;
  }
  .project-info-modal-name {
    font-size: 40px !important;
  }
  .skill-icons {
    font-size: 35px !important;
    margin-left: 18px !important;
  }
  .project-info-desc-container .project-description {
    font-size: 20px;
  }
}
</style>
