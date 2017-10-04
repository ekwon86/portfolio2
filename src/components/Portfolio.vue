<template>
    <div id="Portfolio">
        <div class="portfolio-content"></div>
    </div>
</template>

<script>
    export default{
        data(){
            return {
            }
        }
    }
</script>

<style lang="scss">
    #Portfolio {
        height: 1000px;
        position: relative;
        width: 100vw;
        border: 1px solid red;
        background-color: white;
        padding: 5% 15%;
        .portfolio-content {
            position: relative;
            top: 50%;
            width: 100%;
            transform:translateY(-50%);
            height: 100%;
            border: 1px solid blue;
        }
    }
</style>
