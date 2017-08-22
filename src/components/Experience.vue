<template>
    <div class="experience-section" id="experience">
        <div class="overlay">
            <h1 class="headings experience-heading">Experience</h1>
            <div class="experience-master">
                <div class="experience-left experience-container">
                    <div class="experience">
                        <h3>2011 - 2013</h3>
                        <h4>CJ PRO</h4>
                        <h4>Superintendent / Project Manager</h4>
                    </div>
                </div>
                <div class="experience-right experience-container">
                    <div class="experience"></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {

            }
        }
    }
</script>

<style lang="scss" scoped>
    .experience {
        border: 1px solid black;
        min-height: 50px;
        height: auto;
    }
    /*.experience-heading {*/
        /*color: white;*/
    /*}*/
    .experience-master {
        margin-top: 5vh;
    }
    .experience-section {
        text-align: center;
        min-height: 80vh;
        width: 100%;
        height: auto;
        padding: 5% 10%;
        /*background-image: url("../assets/bg4.png");*/
        background-position: center;
        background-attachment: fixed;
        background-size: cover;
    }
    .experience-container {
        height: 50vh;
    }
    .experience-left {
        border: 1px solid rgba(0,0,0,0.25);
        width: 50%;
        float: left;
        padding: 3%;
        .experience {
            text-align: right;
        }
    }
    .experience-right {
        border: 1px solid rgba(0,0,0,0.25);
        width: 50%;
        float: right;
        padding: 3%;
        .experience {
            text-align: left;
        }
    }
</style>