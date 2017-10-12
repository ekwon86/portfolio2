<template>
    <div id="Landing">
        <div class="parallax-bg" id="particles-js"></div>
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
            </div>
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
    #Landing {
        height: 100vh;
        width: 100%;
    }
    #particles-js {
        background-color: #393939;
        position: fixed;
        z-index: -100;
        width: 100%;
    }
    .parallax-bg {
        height: 100vh;
        position: absolute;
        top: 0;
        left: 0;
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
        position: fixed;
        z-index: -100;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        overflow: hidden;
    }
    .eklogo {
        height: 12em;
        position: relative;
        width: 12em;
    }

    .name-container {
        width: 100%;
        position: relative;
        top: 50%;
        transform: translate(0,-50%);
        -ms-transform: translateY(-50%);
        -webkit-transform: translateY(-50%);
        -moz-transform: translateY(-50%);
        -o-transform: translateY(-50%);
        text-align: center;
        .name {
            font-family: 'Teko', sans-serif;
            font-size: 9em;
            text-transform: uppercase;
            font-weight: lighter;
            letter-spacing: 0.3em;
            text-shadow: 4px 4px rgba(0, 0, 0, 0.09);
            font-style: normal;
            color: rgba(255, 255, 255, 1);
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

    /*MOBILE VIEW*/
    @media (min-width: 320px) and (max-width: 480px) {
        #Landing {
            display: none;
        }
        #particles-js {
            display: none;
        }

        .content-a {
            background-color: grey;
        }

        .eklogo {
            height: 10em;
            width: 10em;
        }

        .name {
            font-size: 3em !important;
        }

        .name-subtext {
            font-size: 1.5em !important;
        }
    }
</style>