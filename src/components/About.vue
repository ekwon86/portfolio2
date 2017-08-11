<template>
    <div class="about-section">
        <div class="about-container">
            <p class="headings about-me-heading">About Me</p>
            <!--<img src="../assets/pic.png" class="img-circle" width="15%" height="15%">-->
            <p class="about-subtext">I am a Front-End Web Developer with proficiency in JavaScript, jQuery, AngularJS, HTML, CSS, and Bootstrap. Formerly a Project Manager / Estimator in the construction industry by trade but fascinated by the challenges coding offered, I have made the jump to web development and am currently seeking opportunities in the Orange County and Los Angeles Areas.</p>
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
    .img-circle {
        border-radius: 999em;
    }
    .about-section {
        padding: 5% 18%;
        min-height: 50vh;
        position: relative;
        height: auto;
        width: 100%;
        text-align: center;
    }
    .about-subtext {
        line-height: 5vh;
        font-weight: lighter;
        text-align: center;
    }
</style>