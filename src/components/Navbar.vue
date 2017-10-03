<template>
    <transition name="slide-fade">
        <div id="navbar" v-if="showNav">
            <div class="navbar-content left-navbar">
                <a href="#">
                    <img src="../assets/logo.png" class="navbar-logo-content"  alt="headerlogo" id="ekheaderlogo">
                    <h3 class="navbar-logo-content navbar-logo-name-text">Eugene Kwon</h3>
                </a>
            </div>
            <!--<div class="navbar-content right-navbar">-->
                <!--<div class="navbar-anchor-holder">-->
                    <!--<a href="#" class="navbar-anchor">-->
                        <!--<span class="navbar-links">Home</span>-->
                    <!--</a>-->
                <!--</div>-->
                <!--<div class="navbar-anchor-holder">-->
                    <!--<a href="#" class="navbar-anchor">-->
                        <!--<span class="navbar-links">Home</span>-->
                    <!--</a>-->
                <!--</div>-->
            <!--</div>-->
        </div>
    </transition>
</template>

<script>
    export default{
        props: ['showNav'],
        data(){
            return {
            }
        }
    }
</script>

<style lang="scss">
    #navbar {
        height: 75px;
        background-color: #2e2e2e;
        position: fixed;
        width: 100%;
        box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
        z-index: 9999;
        font-size: 0;
        padding: 0 15%;
        #ekheaderlogo {
            height: 100%;
            margin-right: 10px;
        }
        .navbar-anchor-holder {
            height: 100%;
            border: 1px solid white;
            width: 50px;
            display: inline-block;
        }

        .navbar-links {
            color: white;
            text-transform: uppercase;
            letter-spacing: 5px;
            font-size: 18px;
            font-family: 'Teko', sans-serif;
            position: relative;
            top: 50%;
            transform: translateY(-50%);
            -ms-transform: translateY(-50%);
            -webkit-transform: translateY(-50%);
            -moz-transform: translateY(-50%);
            -o-transform: translateY(-50%);
        }
        .navbar-logo-content {
            display: inline-block;
        }
        .navbar-logo-name-text {
            color: white;
            position: relative;
            text-transform: uppercase;
            letter-spacing: 5px;
            font-family: 'Teko', sans-serif;
            top: 50%;
            transform: translateY(-50%);
            -ms-transform: translateY(-50%);
            -webkit-transform: translateY(-50%);
            -moz-transform: translateY(-50%);
            -o-transform: translateY(-50%);
        }
        .left-navbar {
            width: 25%;
            text-align: left;
        }
        .right-navbar {
            width: 75%;
            text-align: right;
            border: 1px solid white;
        }
        .navbar-content {
            height: 50px;
            vertical-align: top;
            display: inline-block;
            position: relative;
            top: 50%;
            transform: translate(0,-50%);
            -ms-transform: translateY(-50%);
            -webkit-transform: translateY(-50%);
            -moz-transform: translateY(-50%);
            -o-transform: translateY(-50%);
        }
    }
    .slide-fade-enter-active {
        transition: all .3s ease;
    }
    .slide-fade-leave-active {
        transition: all .3s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }
    .slide-fade-enter, .slide-fade-leave-to
        /* .slide-fade-leave-active below version 2.1.8 */ {
        transform: translateY(-40px);
        -ms-transform: translateY(-40px);
        -webkit-transform: translateY(-40px);
        -moz-transform: translateY(-40px);
        -o-transform: translateY(-40px);
        opacity: 0;
    }
</style>