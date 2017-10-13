<template>
    <transition name="slide-fade">
        <div id="navbar" v-if="showNav">
            <div class="navbar-content left-navbar">
                <a href="#">
                    <img src="../assets/logo.png" class="navbar-logo-content"  alt="headerlogo" id="ekheaderlogo">
                    <h3 class="navbar-logo-content navbar-logo-name-text">Eugene Kwon</h3>
                </a>
            </div>
            <div class="navbar-content right-navbar">
              <a href="#" v-scroll-to="{el: '#Landing', offset: spacerHeight, duration: 500}">
                <p class="navbar-links">Home</p>
              </a>
              <a href="#" v-scroll-to="{el: '#About', offset: spacerHeight, duration: 500}">
                <p class="navbar-links">About</p>
              </a>
              <a href="#" v-scroll-to="{el: '#Skills', offset: spacerHeight, duration: 500}">
                <p class="navbar-links">Skills</p>
              </a>
              <a href="#" v-scroll-to="{el: '#Portfolio', offset: spacerHeight, duration: 500}">
                <p class="navbar-links">Portfolio</p>
              </a>
              <a href="#" v-scroll-to="{el: '#Experience', offset: spacerHeight, duration: 500}">
                <p class="navbar-links">Experience</p>
              </a>
            </div>
        </div>
    </transition>
</template>

<script>
    export default{
        props: ['showNav'],
        data(){
            return {
              spacerHeight: 0
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
        .navbar-links {
          position: relative;
          top: 50%;
          font-size: 15px;
          text-transform: uppercase;
          color: white;
          transition: 0.2s;
          letter-spacing: 3px;
          margin: 0;
          display: inline-block;
          margin-left: 25px;
          transform: translateY(-50%);
          -ms-transform: translateY(-50%);
          -webkit-transform: translateY(-50%);
          -moz-transform: translateY(-50%);
          -o-transform: translateY(-50%);
          &:hover {
            color: #36beeb;
          }
        }
        .navbar-anchor-holder {
            height: 100%;
            width: 50px;
            display: inline-block;
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
        transition: all .8s ease;
    }
    .slide-fade-leave-active {
        transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
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

    /*MOBILE VIEW*/
    @media (min-width: 320px) and (max-width: 480px) {
        #navbar {
            display: none;
        }
    }

    /*MOBILE VIEW - LANDSCAPE*/
    @media (min-width: 481px) and (max-width: 800px) {
        #navbar {
            display: none;
        }
    }

    /*LAPTOPS*/
    @media (min-width: 1025px) and (max-width: 1280px) {
        #navbar {
            padding: 0 10%;
        }
        #navbar .left-navbar {
            width: 35%;
        }
        #navbar .right-navbar {
            width: 65%;
        }
    }
</style>
