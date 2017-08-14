<template>
    <div class="experience-section" id="experience">
        <h1 class="headings">Experience</h1>
        <div class="experience-master">
            <div class="experience-left experience-container">

            </div>
            <div class="experience-right experience-container"></div>
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

    .experience-master {
        margin-top: 5vh;
    }
    .experience-section {
        text-align: center;
        min-height: 80vh;
        width: 100%;
        height: auto;
        padding: 5% 10%;
    }
    .experience-container {
        height: 50vh;
    }
    .experience-left {
        border: 1px solid black;
        width: 50%;
        float: left;
    }
    .experience-right {
        border: 1px solid black;
        width: 50%;
        float: right;
    }
</style>