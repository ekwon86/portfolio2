<template>
    <div class="skills-section" id="skills">
        <div class="overlay">
            <h1 class="headings skills-heading">skills</h1>
            <div class="row skills-container">
                <transition name="slide-fade-left">
                    <div class="col-xs-12 col-md-4 skills-main">
                        <div class="skills-sub">
                            <img src="../assets/computer.png" class="skills-icons" alt="frontend">
                            <p class="sub-headings skills-sub-headings">Front-End</p>
                            <div v-for="skill in frontEnd" class="skill-indiv-container" v-on:mouseover="mouseOverSkill">
                                <div class="icon-container">
                                    <i :class="'skill-icon devicon-' + skill.icon" data-toggle="tooltip" :title="skill.lang"></i>
                                </div>
                                <div class="percentage-container" style="text-align: right;">
                                    <div class="percentage" :style="'width:' + skill.percentage + '%'">
                                        <!--<span class="percentage-text">{{ skill.percentage }}%</span>-->
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </transition>
                <transition name="slide-fade-bottom">
                    <div class="col-xs-12 col-md-4 skills-main">
                        <div class="skills-sub">
                            <img src="../assets/hierarchy-structure.png"  class="skills-icons" alt="backend">
                            <p class="sub-headings skills-sub-headings">Back-End</p>
                            <div v-for="skill in backEnd" class="skill-indiv-container">
                                <div class="icon-container">
                                    <i :class="'skill-icon devicon-' + skill.icon" data-toggle="tooltip" :title="skill.lang"></i>
                                </div>
                                <div class="percentage-container">
                                    <div class="percentage" :style="'width:' + skill.percentage + '%'"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </transition>
                <transition name="slide-fade-right">
                    <div class="col-xs-12 col-md-4 skills-main">
                        <div class="skills-sub">
                            <img src="../assets/edit-tools.png" class="skills-icons" alt="tools">
                            <p class="sub-headings skills-sub-headings">Additional</p>
                            <div v-for="skill in misc" class="skill-indiv-container">
                                <div class="icon-container">
                                    <i :class="'skill-icon devicon-' + skill.icon" data-toggle="tooltip" :title="skill.skill"></i>
                                </div>
                                <div class="percentage-container">
                                    <div class="percentage" :style="'width:' + skill.percentage + '%'"></div>
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
                    { lang: 'HTML', icon: 'html5-plain', percentage: '90' },
                    { lang: 'CSS', icon: 'css3-plain', percentage: '100'},
                    { lang: 'Javascript', icon: 'javascript-plain', percentage: '90'},
                    { lang: 'Vue', icon: 'vuejs-plain', percentage: '90' },
                    { lang: 'React', icon: 'react-original', percentage: '75' },
                    { lang: 'Angular', icon: 'angularjs-plain', percentage: '60' },
                    { lang: 'jQuery', icon: 'jquery-plain', percentage: '90' },
                    { lang: 'Bootstrap', icon: 'bootstrap-plain', percentage: '100' },
                    { lang: 'Sass', icon: 'sass-original', percentage: '100' },
                    { lang: 'Less', icon: 'less-plain-wordmark', percentage: '100'},
                ],
                backEnd: [
                    { lang: 'NodeJS', icon: 'nodejs-plain', percentage: '60' },
                    { lang: 'PHP', icon: 'php-plain', percentage: '60' },
                    { lang: 'Express', icon: 'express-original', percentage: '60' },
                    { lang: 'MongoDB', icon: 'mongodb-plain', percentage: '60' },
                    { lang: 'MySQL', icon: 'mysql-plain', percentage: '60'}
                ],
                misc: [
                    { skill: 'Version Management (Git)', icon: 'git-plain', percentage: '70' },
                    { skill: 'Babel', icon: 'babel-plain', percentage: '60' },
                    { skill: 'Webpack', icon: 'webpack-plain', percentage: '60' },
                    { skill: 'Chrome Dev Tools', icon: 'chrome-plain', percentage: '70' },
                    { skill: 'Grunt', icon: 'grunt-line', percentage: '60' },
                    { skill: 'Gulp', icon: 'gulp-plain',  percentage: '60' },
                    { skill: 'Bower', icon: 'bower-plain', percentage: '60' },
                    { skill: 'Heroku', icon: 'heroku-original',  percentage: '60' },
                    { skill: 'Atom', icon: 'atom-original',  percentage: '90' },
                    { skill: 'Webstorm', icon: 'webstorm-plain',  percentage: '100' },
                    { skill: 'PHPStorm', icon: 'phpstorm-plain', percentage: '100' },
                    { lang: 'Wordpress', icon: 'wordpress-plain',percentage: '60' },
                    { skill: 'Photoshop', icon: 'photoshop-plain', percentage: '60'},
                    { skill: 'Illustrator', icon: 'illustrator-plain', percentage: '60' }
                ]
            }
        },
        methods: {
            mouseOverSkill(e){
                console.log(e.target);
            }
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
        min-height: 80vh;
        height: auto;
        background: url("../assets/bg7.png") 0px 0px fixed;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        .overlay {
            height: 100%;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.75);
            position: relative;
            padding: 5% 10%;
        }
    }
    .skills-icons {
        width: 75px;
    }

    .skill-indiv-container {
        width: 100%;
        margin: 10px 0;
        height: 50px;
        border: 1px solid rgba(0,0,0,0.05);
        transition: 0.2s ease;
        .icon-container {
            height: 100%;
            width: 20%;
            float: left;
            padding: 10px;
            .skill-icon {
                font-size: 30px;
            }
        }
        .percentage-container {
            width: 80%;
            float: right;
            height: 100%;
            text-align: left;
            padding: 10px;
            .percentage {
                border: 1px solid rgba(0, 214, 70, 1);
                height: 10px;
                background-color: rgba(0, 214, 70, 1);
                position: relative;
                top: 50%;
                transform: translate(0,-50%);
            }
        }
        &:hover {
            background-color: rgba(0,0,0,0.5);
            * {
                color: white;
            }
        }
    }

    .skills-container {
        height: auto;
        margin-top: 3%;
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
        margin: 5% 0;
        padding-bottom: 2%;
        border-bottom: 1px solid rgba(0,0,0,0.1);
    }


</style>