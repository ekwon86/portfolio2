<template>
    <div class="experience-section text-center" id="Experience">
        <div class="background-split">
            <div class="overlay"></div>
            <div class="background-split-left splits text-right">
                <div class="split-content split-content-left">
                    <h4 class="sub-headings edu-heading width-float-right">education</h4>
                    <div class="edu-exp-sub-holders">
                        <transition name="slide-fade-right">
                            <div v-if="expScrolledTo" class="width-float-right">
                                <h4 class="edu-exp-sub-headings">Learning Fuze Web Development Bootcamp</h4>
                                <p>March 2016 - June 2017</p>
                                <p>Over 700 hours of full-immersion software development</p>
                                <p>Curriculum Highlights: HTML5, CSS3, Javascript, jQuery, AngularJS, PHP, MySQL, Firebase, Version Management</p>
                            </div>
                        </transition>
                    </div>
                    <div class="edu-exp-sub-holders">
                        <transition name="slide-fade-right">
                            <div v-if="expScrolledTo" class="width-float-right">
                                <h4 class="edu-exp-sub-headings">California State University, Fullerton</h4>
                                <em>Bachelor of Arts, International Business</em><br/>
                                <em>Concentration in Japanese</em>
                                <p>2004-2010</p>
                            </div>
                        </transition>
                    </div>
                </div>
            </div>
            <div class="background-split-right splits text-left">
                <div class="split-content">
                    <h4 class="sub-headings exp-heading width-float-left">experience</h4>
                    <div class="edu-exp-sub-holders">
                        <transition name="slide-fade-left">
                            <div v-if="expScrolledTo" class="width-float-left">
                                <h4 class="edu-exp-sub-headings">Laser App Software / iPipeline</h4>
                                <em>Front End Developer&nbsp;&nbsp;&nbsp;/&nbsp;&nbsp;&nbsp;Associate, UI Developer</em>
                                <p><strong>September 2016 to Present</strong></p>
                                <p>Utilized the VueJS library to create a user interface for an account opening process integration system.</p>
                                <p>Created internal office tool utilizing NodeJS to automate onboarding process for new clients</p>
                                <p>Designed layout for the annual conference website utilizing the Wordpress content management system</p>
                                <p>Responsible for designing micro sites</p>
                            </div>
                        </transition>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['expScrolledTo'],
        data() {
            return {
            }
        },
        methods: {
            slideEduLeft(){
                this.slideEdu = true;
            }
        }
    }
</script>

<style lang="scss" scoped>
    .slide-fade-right-enter-active {
        transition: all .3s ease;
    }
    .slide-fade-right-leave-active {
        transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }
    .slide-fade-right-enter, .slide-fade-right-leave-to
        /* .slide-fade-leave-active below version 2.1.8 */ {
        transform: translateX(-100px);
        -ms-transform: translateX(-100px);
        -webkit-transform: translateX(-100px);
        -moz-transform: translateX(-100px);
        -o-transform: translateX(-100px);
        opacity: 0;
    }

    .slide-fade-left-enter-active {
        transition: all .3s ease;
    }
    .slide-fade-left-leave-active {
        transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }
    .slide-fade-left-enter, .slide-fade-left-leave-to
        /* .slide-fade-leave-active below version 2.1.8 */ {
        transform: translateX(100px);
        -ms-transform: translateX(100px);
        -webkit-transform: translateX(100px);
        -moz-transform: translateX(100px);
        -o-transform: translateX(100px);
        opacity: 0;
    }

    .width-float-right {
        width: 80%;
        float: right;
        margin-bottom: 40px;
    }
    .width-float-left {
        width: 80%;
        float: left;
    }

    #Experience {
        z-index: 999;
        position: relative;
        height: 800px;
        .background-split {
            position: absolute;
            width: 100vw;
            height: 100%;
            background-color: white;
            z-index: -999;
            background:url('../assets/okOf0aq.png') 0px 0px fixed;
            background-position: center;
            background-repeat: no-repeat;
            background-size: cover;
            .overlay {
                position: absolute;
                height: 100%;
                width: 100%;
                top: 0;
                left: 0;
                background-color: rgba(255, 81, 79, 0.84);
                z-index: -1
            }
            .edu-exp-sub-holders {
                min-height: 15vh;
                height: auto;
                margin-bottom: 5%;
            }
            .background-split-left {
                height: 100%;
                width: 50%;
                float: left;
                background-color: rgba(14, 255, 243, 0.75);
                color: white;
                padding-right: 2%;
                /*box-shadow: 0 19px 38px rgba(0,0,0,0.30), 0 15px 12px rgba(0,0,0,0.22);*/
                padding-left: 5%;
                * {
                    color: white;
                }
            }
            .background-split-right {
                height: 100%;
                width: 50%;
                float: right;
                padding-right: 5%;
                padding-left: 2%;
                * {
                    color: white;
                }
            }
            .sub-headings {
                letter-spacing: 0.5vw;
                font-family: 'Teko', sans-serif;
                text-transform: uppercase;
                font-size: 4em;
                padding-bottom: 15px;
                margin-bottom: 50px;
            }
            .edu-heading {
                border-bottom: 1px solid white;
            }
            .exp-heading {
                border-bottom: 1px solid white;
            }
        }
        .splits {
            .edu-exp-sub-headings {
                font-weight: bold;
            }
        }
        .split-content {
            height: auto;
            min-height:500px;
            position: relative;
            top: 50%;
            transform: translateY(-50%);
            -ms-transform: translateY(-50%);
            -webkit-transform: translateY(-50%);
            -moz-transform: translateY(-50%);
            -o-transform: translateY(-50%);
        }
        .experience-container {
            height: 80%;
            padding: 0 5%;
            .experience-education-container {
                margin-top: 3%;
                height: 100%;
                border: 1px solid black;
                .sub-headings {
                    text-transform: uppercase;
                    letter-spacing: 0.5vw;
                    font-size: 1.5em;
                }
                .experience-sub-container {
                    width: 50%;
                    height: 100%;
                    float: left;
                    text-align: right;
                    padding: 1%;
                    border-right: 1px solid black;
                }
                .education-sub-container {
                    width: 50%;
                    height: 100%;
                    float: right;
                    text-align: left;
                    padding: 1%;
                }
            }
        }
    }
    @media (min-width: 320px) and (max-width: 480px) {
        .background-split-left {
            padding-left: 0 !important;
        }
        .background-split-right {
            padding-right: 0 !important;
        }
        .sub-headings {
            font-size: 2em !important;
            padding-bottom: 5px !important;
            margin-bottom: 20px !important;
        }
        .edu-exp-sub-headings {
            font-size: 1em;
        }
        em {
            margin-bottom: 10px;
        }
        p, em{
            font-size: 12px;
        }
    }
</style>