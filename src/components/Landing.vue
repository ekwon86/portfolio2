<template>
    <div class="parallax-bg" id="particles-js">
        <div class="overlay content-a">
            <div class="name-container">
                <transition name="slide-fade-top">
                    <img src="../assets/logo.png" class="eklogo" alt="logo" v-if="showLanding">
                </transition>
                <transition name="slide-fade-top">
                    <p class="name" v-if="showLanding">Eugene Kwon</p>
                </transition>
                <transition name="slide-fade-bottom">
                    <p class="name-subtext" v-if="showLanding">Front-End Web Developer</p>
                </transition>
                <transition name="slide-fade-bottom">
                    <div v-if="showLanding" class="start-btn">Start</div>
                </transition>
            </div>
            <!--<div class="arrow-down" v-on:click="arrowClick"></div>-->
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            showLanding: false,
            showArrow: false,
            btnEntered: false
        }
    },
    methods: {
        arrowClick(){
            alert('test');
        }
    },
    mounted: function(){
        let self = this;
        setTimeout(function(){
            self.showLanding = true;
        }, 500);
    }
}
</script>

<style lang="scss" scoped>
    #particles-js {
        background-color: #393939;
        position: fixed;
        z-index: -999;
        width: 100vw;
    }
    .parallax-bg {
        /*background-image: url("../assets/bg.png");*/
        height: 100vh;
        background-attachment: fixed;
        background-position: 50% 50%;
        background-repeat: no-repeat;
        background-size: cover;
        .overlay {
            height: 100%;
            position: absolute;
            width: 100%;
            background-color: rgba(53, 53, 53, 0.3);
            padding: 15%;
            z-index: 999;
        }
    }
    .content-a {
        width: 100%;
        height: 100%;
        overflow: hidden;
    }
    .eklogo {
        height: 12em;
        position: relative;
        width: 12em;
    }


    .arrow-down{
        position: absolute;
        bottom: 110px;
        left: 50%;
        margin-left: -10px;
        width: 21px;
        height: 29px;
        background: url(../assets/arrow-down.png) no-repeat center center;
        display: block;
        -webkit-animation: bounce-fade 1.2s infinite;
        -moz-animation:    bounce-fade 1.2s infinite;
        -o-animation:      bounce-fade 1.2s infinite;
        animation:        bounce-fade 1.2s infinite;
        &:hover {
            cursor: pointer;
        }
    }

    .start-btn {
        color: white;
        font-size: 2em;
        text-transform: uppercase;
        letter-spacing: 10px;
        padding: 10px 50px;
        border: 5px solid white;
        display: inline-block;
        margin-top: 100px;
        transition: 0.3s;
        font-family: 'Oswald', sans-serif;
        &:hover {
            cursor: pointer;
            background-color: white;
            color: #36beeb;
            font-weight: 300;
        }
    }

    @-webkit-keyframes bounce-fade {
        0%   { opacity: 0; bottom: 70px; }
        100% { opacity: 1; bottom: 35px; }
    }
    @-moz-keyframes bounce-fade {
        0%   { opacity: 0; bottom: 70px; }
        100% { opacity: 1; bottom: 35px; }
    }
    @-o-keyframes bounce-fade {
        0%   { opacity: 0; bottom:70px; }
        100% { opacity: 1; bottom: 35px; }
    }
    @keyframes bounce-fade {
        0%   { opacity: 0; bottom: 70px; }
        100% { opacity: 1; bottom: 35px; }
    }

    .name-container {
        width: 100%;
        position: relative;
        top: 50%;
        transform: translate(0,-50%);
        text-align: center;
        .name {
            font-family: 'Oswald', sans-serif;
            font-size: 6em;
            text-transform: uppercase;
            font-weight: lighter;
            letter-spacing: 0.5em;
            text-shadow: 4px 4px rgba(0, 0, 0, 0.09);
            font-style: normal;
            color: rgba(255, 255, 255, 1);
            /*text-shadow: 1px 1px #515151;*/
        }
        .name-subtext {
            color: rgba(255,255,255, 1);
            font-size: 2.5em;
            letter-spacing: 0.1em;
        }
    }
    .active {
        position: relative;
        top: 50px;
    }

    .scroll-button {
        &:hover {
            cursor: pointer;
        }
        span {
            color: white;
        }
    }

    .fade-in-enter-active {
        transition: all .3s ease;
    }

    .fade-in-leave-active {
        transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }

    .fade-in-enter, .fade-in-leave-to{
        opacity: 0;
    }


    .slide-fade-top-enter-active {
        transition: all .3s ease;
    }
    .slide-fade-top-leave-active {
        transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }
    .slide-fade-top-enter, .slide-fade-top-leave-to{
        transform: translateY(-75px);
        opacity: 0;
    }

    .slide-fade-bottom-enter-active {
        transition: all .3s ease;
    }
    .slide-fade-bottom-leave-active {
        transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }
    .slide-fade-bottom-enter, .slide-fade-bottom-leave-to{
        transform: translateY(75px);
        opacity: 0;
    }

</style>