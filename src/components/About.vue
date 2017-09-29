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
        text-align: center;
        background-color: white;
    }
    .about-subtext {
        line-height: 5vh;
        font-weight: lighter;
        text-align: center;
    }
    .about-container {
        position: relative;
        padding: 0 15vw;
        top: 50%;
        transform:translate(0,-50%);
    }
</style>