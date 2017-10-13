<template>
    <div class="skills-section" id="Skills">
        <div class="overlay">
            <h1 class="headings skills-heading">skills</h1>
            <div class="row skills-container">
                <transition name="slide-fade-left">
                    <div class="col-xs-12 col-md-4 skills-main">
                        <div class="skills-sub">
                            <p class="sub-headings skills-sub-headings">Front-End</p>
                            <div v-for="skill in frontEnd" class="skills-holder">
                                <div class="skill-holder-icon-holder">
                                    <i :class="'devicon-' + skill.icon + ' devicons'" data-toggle="tooltip" :title="skill.lang"></i>
                                </div>
                                <div class="skill-holder-progress-bar-holder">
                                    <div class="skill-level-bar">
                                        <div class="frontend-level-bar level-bar"></div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </transition>
                <transition name="slide-fade-bottom">
                    <div class="col-xs-12 col-md-4 skills-main">
                        <div class="skills-sub">
                            <p class="sub-headings skills-sub-headings">Back-End</p>
                            <div v-for="skill in backEnd" class="skills-holder">
                                <div class="skill-holder-icon-holder">
                                    <i :class="'devicon-' + skill.icon + ' devicons'" data-toggle="tooltip" :title="skill.lang"></i>
                                </div>
                                <div class="skill-holder-progress-bar-holder">
                                    <div class="skill-level-bar">
                                        <div class="backend-level-bar level-bar"></div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </transition>
                <transition name="slide-fade-right">
                    <div class="col-xs-12 col-md-4 skills-main">
                        <div class="skills-sub">
                            <p class="sub-headings skills-sub-headings">Additional</p>
                            <div v-for="skill in misc" class="skills-holder">
                                <div class="skill-holder-icon-holder">
                                    <i :class="'devicon-' + skill.icon + ' devicons'" data-toggle="tooltip" :title="skill.lang"></i>
                                </div>
                                <div class="skill-holder-progress-bar-holder">
                                    <div class="skill-level-bar">
                                        <div class="misc-level-bar level-bar"></div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </transition>
            </div>
            <div class="row text-center hover-over-me-text">
                <div class="col-md-12">
                    <small><em>*** &nbsp;Please hover over icon to view name of technology </em></small>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['showSkills'],
        data(){
            return {
                frontEnd: [
                    { lang: 'HTML', icon: 'html5-plain colored', percentage: '100' },
                    { lang: 'CSS', icon: 'css3-plain colored', percentage: '100'},
                    { lang: 'Javascript', icon: 'javascript-plain colored', percentage: '90'},
                    { lang: 'Vue', icon: 'vuejs-plain colored', percentage: '90' },
                    { lang: 'React', icon: 'react-original colored', percentage: '75' },
                    { lang: 'Angular', icon: 'angularjs-plain colored', percentage: '75' },
                    { lang: 'jQuery', icon: 'jquery-plain colored', percentage: '90' },
                    { lang: 'Bootstrap', icon: 'bootstrap-plain colored', percentage: '100' },
                    { lang: 'Typescript', icon: 'typescript-plain colored', percentage: '75'},
                    { lang: 'Sass', icon: 'sass-original colored', percentage: '100' }
                ],
                backEnd: [
                    { lang: 'NodeJS', icon: 'nodejs-plain colored', percentage: '75' },
                    { lang: 'Express', icon: 'express-original colored', percentage: '75' },
                    { lang: 'MongoDB', icon: 'mongodb-plain colored', percentage: '75' },
                    { lang: 'PHP', icon: 'php-plain colored', percentage: '60' },
                    { lang: 'MySQL', icon: 'mysql-plain colored', percentage: '50'}
                ],
                misc: [
                    { lang: 'Version Management (Git)', icon: 'git-plain colored', percentage: '70' },
                    { lang: 'Heroku', icon: 'heroku-original colored',  percentage: '60' },
                    { lang: 'Webpack', icon: 'webpack-plain colored', percentage: '60' },
                    { lang: 'Grunt', icon: 'grunt-line colored', percentage: '60' },
                    { lang: 'Gulp', icon: 'gulp-plain colored',  percentage: '60' },
                    { lang: 'Bower', icon: 'bower-plain colored', percentage: '60' },
                    { lang: 'Atom', icon: 'atom-original colored',  percentage: '100' },
                    { lang: 'Webstorm', icon: 'webstorm-plain colored',  percentage: '100' },
                    { lang: 'Wordpress', icon: 'wordpress-plain colored',percentage: '80' },
                    { lang: 'Photoshop', icon: 'photoshop-plain colored', percentage: '60'},
                    { lang: 'Illustrator', icon: 'illustrator-plain colored', percentage: '60' }
                ],
                percentageArray: []
            }
        },
        methods: {
            animateFrontEndWidth() {
                let index = 0;
                const frontEndBars = document.getElementsByClassName("frontend-level-bar");
                for (let i = 0; i < frontEndBars.length; i++) {
                    let current = frontEndBars[i];
                    current.style.width = this.frontEnd[index].percentage + '%';
                    index++;
                }
            },
            animateBackEndWidth() {
                let index = 0;
                const backEndBars = document.getElementsByClassName("backend-level-bar");
                for (let i = 0; i < backEndBars.length; i++) {
                    let current = backEndBars[i];
                    current.style.width = this.backEnd[index].percentage + '%';
                    index++;
                }
            },
            animateMiscWidth() {
                let index = 0;
                const miscBars = document.getElementsByClassName("misc-level-bar");
                for (let i = 0; i < miscBars.length; i++) {
                    let current = miscBars[i];
                    current.style.width = this.misc[index].percentage + '%';
                    index++;
                }
            },
            triggerAllWidthAnimations() {
                setTimeout(() => {
                    this.animateFrontEndWidth();
                }, 100);
                setTimeout(() => {
                    this.animateBackEndWidth();
                }, 300);
                setTimeout(() => {
                    this.animateMiscWidth();
                }, 500);
            },
            checkScroll() {
                const skillSection = document.getElementById('Skills');
                const topOfSkillSection = skillSection.getBoundingClientRect().top;

                if (topOfSkillSection <= 250) {
                    this.triggerAllWidthAnimations();
                }
            }
        },
        created() {
            window.addEventListener('scroll', this.checkScroll);
        }
    }
</script>

<style lang="scss" scoped>
    $blue: #0eb7da;
    .open-card {
        width: 100% !important;
        padding: 5% !important;
    }
    .skills-section {
        text-align: left;
        height: auto;
        background: url("../assets/bg7.png") 0px 0px fixed;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        .skills-heading {
            color: #454545;

            border-bottom: 1px solid rgba(0,0,0,0.1);
        }
        .overlay {
            height: 100%;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.75);
            position: relative;
            padding: 5% 15%;
        }
    }
    .level-bar-width {
        width: 50% !important;
    }
    .skills-icons {
        width: 65px;
    }
    .skills-holder {
        margin: 5px 0;
        width: 100%;
        padding: 5px 10px 5px 5px;
        height: 60px;
        .skill-holder-icon-holder {
            width: 20%;
            float: left;
            height: 100%;
            padding: 10px;
            .devicons {
                font-size: 30px;
            }
        }
        .skill-holder-progress-bar-holder {
            width: 75%;
            float: right; height: 100%;
            .skill-level-bar {
                background-color: rgba(0,0,0,0.2);
                height: 20px;
                margin: 4% 0;
                .level-bar {
                    width: 0;
                    height: 100%;
                    background-color: rgba(117, 225, 90, 0.9);
                    transition: 0.5s;
                    -webkit-transition: 0.5s;
                }
            }
        }
    }

    .skills-container {
        height: auto;
        .skills-main {
            height: auto;
            text-align: center;
            padding: 1%;
            width: 33.33%;
            transition: 0.5s;
        }
        .skills-sub {
            background-color: rgba(255,255,255,1);
            height: auto;
            min-height: 100%;
            padding: 5%;
            box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
            transition: all 0.3s cubic-bezier(.25,.8,.25,1);
            border-radius: 1px;
        }
    }

    .skills-sub-headings {
        margin: 1% 0;
        padding-bottom: 2%;
        border-bottom: 1px solid rgba(0,0,0,0.1);
    }

    /*MOBILE VIEW*/
    @media (min-width: 320px) and (max-width: 480px) {
        .skills-section .overlay {
            padding: 10%;
        }
        .hover-over-me-text {
            display: none;
        }
        .skills-container .skills-main {
            width: 100%;
        }
        .skills-container .skills-sub {
            padding: 3%;
        }
        .skills-sub-headings {
            margin: 0;
            font-size: 1.75em;
            padding-bottom: 0;
        }
        .skills-holder {
            border: 1px solid rgba(0,0,0,0.05);
            height: 30px;
        }
        .skills-holder .skill-holder-icon-holder .devicons {
            font-size: 18px;
        }
        .skills-holder .skill-holder-progress-bar-holder .skill-level-bar {
            height: 10px;
        }
        .skills-holder .skill-holder-progress-bar-holder .skill-level-bar {
            margin: 0;
            position: relative;
            top: 50%;
            transform: translateY(-50%);
        }
        .skills-holder .skill-holder-icon-holder {
            padding: 0;
        }
    }

    /*MOBILE VIEW - LANDSCAPE*/
    @media (min-width: 481px) and (max-width: 800px) {
        .skills-section .overlay {
            padding: 5% 10%;
        }
        .hover-over-me-text {
            display: none;
        }
        .skills-container .skills-sub {
            padding: 3%;
        }
        .skills-sub-headings {
            margin: 0;
            font-size: 1.75em;
            padding-bottom: 0;
        }
        .skills-holder {
            border: 1px solid rgba(0,0,0,0.05);
            height: 40px;
        }
        .skills-holder .skill-holder-icon-holder .devicons {
            font-size: 18px;
        }
        .skills-holder .skill-holder-progress-bar-holder .skill-level-bar {
            height: 10px;
        }
        .skills-holder .skill-holder-progress-bar-holder .skill-level-bar {
            margin: 0;
            position: relative;
            top: 50%;
            transform: translateY(-50%);
        }
        .skills-holder .skill-holder-icon-holder {
            padding: 5px;
        }
    }

    /*LAPTOPS*/
    @media (min-width: 1025px) and (max-width: 1280px) {
        #Skills .overlay {
            padding: 5% 10%;
        }
        .skills-sub-headings {
            margin: 0;
            font-size: 2em;
            padding-bottom: 0;
        }
        .skills-holder {
            border: 1px solid rgba(0,0,0,0.05);
            height: 50px;
        }
        .skills-holder .skill-holder-icon-holder .devicons {
            font-size: 30px;
        }
        .skills-holder .skill-holder-progress-bar-holder .skill-level-bar {
            height: 12px;
        }
        .skills-holder .skill-holder-progress-bar-holder .skill-level-bar {
            margin: 0;
            position: relative;
            top: 50%;
            transform: translateY(-50%);
        }
        .skills-holder .skill-holder-icon-holder {
            padding: 5px;
        }
    }
</style>
