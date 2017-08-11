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
                            <div class="devicon-container">
                                <div class="devicon-holder" v-for="skill in frontEnd">
                                    <i :class="'devicon-' + skill.icon + ' devicons spin'" data-toggle="tooltip" :title="skill.lang"></i><br/>
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
                            <div class="devicon-container">
                                <div class="devicon-holder" v-for="skill in backEnd">
                                    <i :class="'devicon-' + skill.icon + ' devicons spin'" data-toggle="tooltip" :title="skill.lang"></i>
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
                            <div class="devicon-container">
                                <div class="devicon-holder" v-for="skill in misc">
                                    <i :class="'devicon-' + skill.icon + ' devicons spin'" data-toggle="tooltip" :title="skill.skill"></i>
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
                    { lang: 'HTML', icon: 'html5-plain' },
                    { lang: 'CSS', icon: 'css3-plain' },
                    { lang: 'Javascript', icon: 'javascript-plain'},
                    { lang: 'Vue', icon: 'vuejs-plain' },
                    { lang: 'React', icon: 'react-original' },
                    { lang: 'Angular', icon: 'angularjs-plain' },
                    { lang: 'jQuery', icon: 'jquery-plain' },
                    { lang: 'Bootstrap', icon: 'bootstrap-plain' },
                    { lang: 'Sass', icon: 'sass-original' },
                    { lang: 'Bower', icon: 'bower-plain' }
                ],
                backEnd: [
                    { lang: 'NodeJS', icon: 'nodejs-plain' },
                    { lang: 'PHP', icon: 'php-plain' },
                    { lang: 'Express', icon: 'express-original' },
                    { lang: 'MongoDB', icon: 'mongodb-plain' },
                    { lang: 'MySQL', icon: 'mysql-plain'}
                ],
                misc: [
                    { skill: 'Version Management (Git)', icon: 'git-plain' },
                    { skill: 'Babel', icon: 'babel-plain' },
                    { skill: 'Webpack', icon: 'webpack-plain' },
                    { skill: 'Chrome Dev Tools', icon: 'chrome-plain' },
                    { skill: 'Grunt', icon: 'grunt-line' },
                    { skill: 'Gulp', icon: 'gulp-plain' },
                    { skill: 'Heroku', icon: 'heroku-original' },
                    { skill: 'Atom', icon: 'atom-original' },
                    { skill: 'Webstorm', icon: 'webstorm-plain' },
                    { skill: 'PHPStorm', icon: 'phpstorm-plain' },
                    { lang: 'Wordpress', icon: 'wordpress-plain' },
                    { skill: 'Photoshop', icon: 'photoshop-plain'},
                    { skill: 'Illustrator', icon: 'illustrator-plain' }
                ]
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
    .skills-heading {
        color: white;
        text-shadow: 1px 1px rgba(0, 0, 0, 0.4);
    }
    .skills-section {
        text-align: center;
        min-height: 80vh;
        height: auto;
        background-image: url("../assets/bg2.png");
        background-attachment: fixed;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        .overlay {
            height: 100%;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.25);
            position: relative;
            padding: 5% 10%;
        }
    }
    .skills-icons {
        width: 100px;
    }
    .devicons {
        font-size: 2.5em;
        border-radius: 100%;
        position: relative;
        border: 1px solid rgba(0,0,0,0.15);
        padding: 15px;
        top: 30%;
        transition: 0.1s;
        &:hover {
            background-color: #515151;
            color: white;
        }
        &::before,
        &::after {
            border-radius: 100%;
        }
    }
    .devicon-container{
        width: 100%;
        height: auto;
        display: flex;
        flex-wrap: wrap;
        position: relative;
    }
    .devicon-holder {
        height: 100px;
        width: 33.33%;
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
            background-color: rgba(255,255,255,0.95);
            height: auto;
            min-height: 100%;
            padding: 10% 5%;
            box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
            transition: all 0.3s cubic-bezier(.25,.8,.25,1);
            border-radius: 1%;
        }
    }

    .skills-sub-headings {
        margin: 5% 0;
        padding-bottom: 2%;
        border-bottom: 1px solid rgba(0,0,0,0.1);
    }

    .slide-fade-left-enter-active {
        transition: all 1s ease;
    }
    .slide-fade-left-leave-active {
        transition: all 1s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }
    .slide-fade-left-enter, .slide-fade-left-leave-to{
        transform: translateX(-100px);
        opacity: 0;
    }

    .slide-fade-right-enter-active {
        transition: all 1s ease;
    }
    .slide-fade-right-leave-active {
        transition: all 1s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }
    .slide-fade-right-enter, .slide-fade-right-leave-to{
        transform: translateX(100px);
        opacity: 0;
    }


    .slide-fade-bottom-enter-active {
        transition: all 1s ease;
    }
    .slide-fade-bottom-leave-active {
        transition: all 1s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }
    .slide-fade-bottom-enter, .slide-fade-bottom-leave-to{
        transform: translateY(100px);
        opacity: 0;
    }

</style>