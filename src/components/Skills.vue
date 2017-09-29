<template>
    <div class="skills-section" id="skills">
        <div class="overlay">
            <h1 class="headings skills-heading">skills</h1>
            <!--<button type="button" v-on:click="animateBorder">CLICK</button>-->
            <div class="row skills-container">
                <transition name="slide-fade-left">
                    <div class="col-xs-12 col-md-4 skills-main">
                        <div class="skills-sub">
                            <p class="sub-headings skills-sub-headings">Front-End</p>
                            <div v-for="skill in frontEnd" class="skills-holder">
                                <div class="skill-holder-icon-holder">
                                    <i :class="'devicon-' + skill.icon + ' devicons spin'" data-toggle="tooltip" :title="skill.lang"></i>
                                </div>
                                <div class="skill-holder-progress-bar-holder">
                                    <div class="skill-level-bar">
                                        <!--<div class="level-bar"></div>-->
                                        <div class="level-bar" v-bind:style="{width: skill.percentage + '%'}"></div>
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
                                    <i :class="'devicon-' + skill.icon + ' devicons spin'" data-toggle="tooltip" :title="skill.lang"></i>
                                </div>
                                <div class="skill-holder-progress-bar-holder">
                                    <div class="skill-level-bar">
                                        <!--<div class="level-bar"></div>-->
                                        <div class="level-bar" v-bind:style="{width: skill.percentage + '%'}"></div>
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
                                    <i :class="'devicon-' + skill.icon + ' devicons spin'" data-toggle="tooltip" :title="skill.lang"></i>
                                </div>
                                <div class="skill-holder-progress-bar-holder">
                                    <div class="skill-level-bar">
                                        <!--<div class="level-bar"></div>-->
                                        <div class="level-bar" v-bind:style="{width: skill.percentage + '%'}"></div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </transition>
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
                    { skill: 'Version Management (Git)', icon: 'git-plain colored', percentage: '70' },
                    { skill: 'Heroku', icon: 'heroku-original colored',  percentage: '60' },
                    { skill: 'Webpack', icon: 'webpack-plain colored', percentage: '60' },
                    { skill: 'Grunt', icon: 'grunt-line colored', percentage: '60' },
                    { skill: 'Gulp', icon: 'gulp-plain colored',  percentage: '60' },
                    { skill: 'Bower', icon: 'bower-plain colored', percentage: '60' },
                    { skill: 'Atom', icon: 'atom-original colored',  percentage: '100' },
                    { skill: 'Webstorm', icon: 'webstorm-plain colored',  percentage: '100' },
                    { lang: 'Wordpress', icon: 'wordpress-plain colored',percentage: '60' },
                    { skill: 'Photoshop', icon: 'photoshop-plain colored', percentage: '60'},
                    { skill: 'Illustrator', icon: 'illustrator-plain colored', percentage: '60' }
                ],
                percentageArray: []
            }
        },
        methods: {
            addToArray(array){
                for (let i = 0; i < array.length; i++){
                    this.percentageArray.push(array[i].percentage);
                }
            },
            animateBorder(){
                let skillBar = document.getElementsByClassName('level-bar');
                let currentPercentage;

                for (let i = 0; i < skillBar.length; i++){
                    for (let j = i; j < this.percentageArray.length; j++){
                        console.log('J is currently ' + j);
                    }
                    skillBar[i].setAttribute("style", "width:" + currentPercentage + "%;");
                }
            }
        },
        mounted(){
            this.addToArray(this.frontEnd);
            this.addToArray(this.backEnd);
            this.addToArray(this.misc);
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
        text-align: center;
        height: auto;
        background: url("../assets/bg7.png") 0px 0px fixed;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        .skills-heading {
            color: #000000;
        }
        .overlay {
            height: 100%;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.75);
            position: relative;
            padding: 5% 10%;
        }
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

</style>