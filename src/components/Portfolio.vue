<template>
    <div id="Portfolio">
        <div class="portfolio-content">
          <p class="headings portfolio-heading">Portfolio</p>
          <div class="project-container">
            <div class="indiv-project-subcontainers" v-for="(project, index) in lfzProjects">
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
                                    <!--Github link-->
                                    <a :href="project.github" target="_blank">
                                        <i class="fa fa-github fa-2x project-icons" aria-hidden="true"></i>
                                    </a>
                                    <!--Info link-->
                                    <i class="fa fa-info-circle fa-2x project-icons" aria-hidden="true" v-on:click="displayModal(index)"></i>
                                    <!--Rocket link-->
                                    <a :href="project.url" target="_blank">
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
        <transition name="fade">
            <div id="project-modal-overlay" v-if="showProjectModal">
                <div class="project-info">
                    <div class="project-info-picture-holder">
                        <i class="fa fa-times-circle exit-icon" aria-hidden="true" v-on:click="closeModal()"></i>
                    </div>
                    <div class="project-info-info-holder"></div>
                </div>
            </div>
        </transition>
    </div>
</template>

<script>
    export default{
        data(){
            return {
                showProjectModal: true,
                lfzProjects: [
                    {
                        name: 'Mega Match Man',
                        id: 'megamatchman',
                        url: 'http://www.eugenekwon.com/projects/megamatchman',
                        github: 'https://github.com/ekwon86/mega_match_man',
                        showContents: false
                    },
                    {
                        name: 'Calculator',
                        id: 'calculator',
                        github: 'https://github.com/ekwon86/calculator',
                        url: 'http://www.eugenekwon.com/projects/calculator',
                        showContents: false
                    },
                    {
                        name: 'Tic-Tac-Toe',
                        id: 'tictactoe',
                        github: 'https://github.com/ekwon86/tictactoe',
                        url: 'http://www.eugenekwon.com/projects/iwant',
                        showContents: false
                    }
                ],
                workProjects: [
                    {
                        name: 'Conference 2017 Site',
                        url: 'http://www.laserapp.com/conference2017',
                        showContents : false
                    }
                ]
            }
        },
        methods: {
            showProjectContents: function(index) {
                this.lfzProjects[index].showContents = true;
            },
            hideProjectContents: function(index) {
                this.lfzProjects[index].showContents = false;
            },
            displayModal(index) {
                this.showProjectModal = true;
                document.body.style.overflow = 'hidden';
                console.log(index);
            },
            closeModal() {
                this.showProjectModal = false;
            }
        }
    }
</script>

<style lang="scss">
    #Portfolio {
        height: 1500px;
        /*position: relative;*/
        width: 100vw;
        background-color: white;
        padding: 5% 15%;
        .portfolio-content {
            position: relative;
            top: 50%;
            width: 100%;
            transform:translateY(-50%);
            height: 100%;
            .portfolio-heading {
              border-bottom: 1px solid rgba(0,0,0,0.1);
            }
        }
    }
    .project-container {
      min-height: 250px;
      font-size: 0;
      height: auto;
      vertical-align: top;
      border: 1px solid rgba(0,0,0,0.25);
    }
    .indiv-project-subcontainers {
      padding: 10px;
      width: 33.33333%;
      display: inline-block;
      height: 250px;
        #megamatchman {
            background: url(../assets/megamatchman.jpg);
        }
        #calculator {
            background: url(../assets/calculator.jpg);
        }
        #tictactoe {
            background: url(../assets/tictactoe.jpg);
        }
    }
    .indiv-project-img-holder {
        height: 100%;
        width: 100%;
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
        background-color: rgba(0,0,0,0.1);
        -moz-transition: all .3s ease;
        -webkit-transition: all .3s ease;
        transition: all .3s ease;
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
        transform:translateY(-50%);
    }
    .indiv-projects-img {
        width: 100%;
        height: 100%;
        background-size: 100% 100% !important;
        background-position: center !important;
    }
    .indiv-projects-overlay:hover {
        background-color: rgba(0,0,0, 0.8);
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
        background-color: rgba(0,0,0,0.6);
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
        transform: translate(0,-50%);
    }
    .project-info-picture-holder {
        position: relative;
        width: 100%;
        height: 60%;
        text-align: right;
        padding: 25px 35px;
        background:url(../assets/megamatchman.jpg);
        background-size: cover;
        background-position: center center;
        .exit-icon {
            font-size: 80px;
            color: white;
            transition: 0.2s;
            &:hover {
                cursor: pointer;
                color: #ff4641;
            }
        }
    }
    .project-info-info-holder {
        height: 40%;
        border-top: 1px solid rgba(0,0,0,0.3);
    }

    /*TRANSITIONS*/
    .slide-fade-top-enter-active {
        transition: all .3s ease;
    }
    .slide-fade-top-leave-active {
        transition: all .3s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }
    .slide-fade-top-enter, .slide-fade-top-leave-to
        /* .slide-fade-leave-active below version 2.1.8 */ {
        transform: translateY(-25px);
        opacity: 0;
    }
    .slide-fade-bottom-enter-active {
        transition: all .3s ease;
    }
    .slide-fade-bottom-leave-active {
        transition: all .3s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }
    .slide-fade-bottom-enter, .slide-fade-bottom-leave-to
        /* .slide-fade-leave-active below version 2.1.8 */ {
        transform: translateY(25px);
        opacity: 0;
    }
    .fade-enter-active, .fade-leave-active {
        transition: opacity .5s
    }
    .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
        opacity: 0
    }
</style>
