<template>
    <div class="parallax-bg">
        <div class="overlay">
            <div class="name-container">
                <transition name="slide-fade-top">
                    <img src="../assets/logo.png" class="eklogo" alt="logo" v-if="showLanding">
                </transition>
                <transition name="slide-fade-top">
                    <p class="name" v-if="showLanding">Eugene Kwon</p>
                </transition>
                <transition name="slide-fade-bottom">
                    <p class="name-subtext" v-if="showLanding">Front-End Web Developer based in the Orange County Area</p>
                </transition>
            </div>
            <div class="arrow-down" v-on:click="arrowClick"></div>
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
    .parallax-bg {
        background-image: url("../assets/bg.png");
        height: 100vh;
        background-attachment: fixed;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        .overlay {
            height: 100%;
            position: relative;
            width: 100%;
            background-color: rgba(222, 184, 175, 0.4);
        }
    }
    .eklogo {
        height: 15em;
        width: 15em;
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
        text-align: center;
        position: relative;
        top: 40%;
        transform: translate(0,-50%);

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
            font-size: 1.5em;
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