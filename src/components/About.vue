<template>
    <div class="about-section" id="About">
        <div class="about-container">
            <p class="headings about-me-heading">About Me</p>
            <!--<img src="../assets/pic.png" class="img-circle" width="15%" height="15%">-->
            <p class="about-subtext">I am a Front-End Web Developer with proficiency in a variety of Front-End and Back-End technologies. Formerly a Project Manager & Estimator in the construction industry by trade but fascinated by the challenges coding offered, I have made the jump to web development and am currently seeking opportunities in the Orange County and Los Angeles Areas.</p>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return {

            }
        }
    }
</script>

<style lang="scss" scoped>
    .about-section {
        height: 40vh;
        width: 100%;
        text-align: left;
        background-color: white;
    }
    .about-subtext {
        line-height: 5vh;
        font-weight: lighter;
        text-align: justify;
    }
    .about-me-heading {
        border-bottom: 1px solid rgba(0,0,0,0.1);
    }
    .about-container {
        position: relative;
        padding: 0 15%;
        top: 50%;
        transform:translate(0,-50%);
        -ms-transform: translateY(-50%);
        -webkit-transform: translateY(-50%);
        -moz-transform: translateY(-50%);
        -o-transform: translateY(-50%);
    }

    /*MOBILE VIEW - PORTRAIT*/
    @media (min-width: 320px) and (max-width: 480px) {
        .about-section {
            height: 80vh;
        }

        .about-container {
            padding: 0 10%;
        }

        .about-subtext {
            font-size: 12px;
        }
    }

    /*MOBILE VIEW - LANDSCAPE*/
    @media (min-width: 481px) and (max-width: 800px) {
        .about-section {
            height: 80vh;
        }
        .about-subtext {
            font-size: 15px;
            line-height: 7vh;
        }

        .about-container {
            padding: 0 10%;
        }
    }

    /*LAPTOPS*/
    @media (min-width: 1025px) and (max-width: 1280px) {
        .about-section {
            height: 50vh;
        }
        .about-container {
            padding: 5% 10%;
        }
    }
</style>
