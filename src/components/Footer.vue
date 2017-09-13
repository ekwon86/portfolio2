<template>
    <div id="footer">
        <div class="overlay">
            <img src="../assets/logo.png" alt="eklogo" class="footer-logo">
            <div class="icon-holder">
                <a href="https://www.github.com/ekwon86" target="_blank">
                    <i class="fa fa-github contact-icons" aria-hidden="true"></i>
                </a>
                <a href="https://www.linkedin.com/in/eugene-kwon-01843836/" target="_blank">
                    <i class="fa fa-linkedin contact-icons" aria-hidden="true"></i>
                </a>
                <a href="https://twitter.com/ekwon86" target="_blank">
                    <i class="fa fa-twitter contact-icons" aria-hidden="true"></i>
                </a>
                <a href="https://angel.co/eugene-kwon" target="_blank">
                    <i class="fa fa-angellist contact-icons" aria-hidden="true"></i>
                </a>
                <a href="mailto:ekwon86@gmail.com" target="_blank">
                    <i class="fa fa-envelope contact-icons" aria-hidden="true"></i>
                </a>
                <i class="fa fa-file-pdf-o contact-icons" aria-hidden="true"></i>
            </div>
            <p>&copy; 2017 Eugene Kwon</p>
        </div>
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

<style lang="scss" scoped>
    $hovercolor: #32a8d0;
    #footer {
        position: relative;
        top: 100vh;
        width: 100%;
        height: 25vh;
        text-align: center;
        background-image: url("../assets/bg.png");
        background-position: bottom;
        background-repeat: no-repeat;
        background-size: cover;
        background-attachment: fixed;
        .overlay {
            height: 100%;
            position: relative;
            width: 100%;
            background-color: rgba(222,184,175,0.4);
            padding: 50px;
            .footer-logo {
                height: 50px;
            }
            .icon-holder {
                margin: 15px 0;
                .contact-icons {
                    color: white;
                    transition: 0.3s;
                    padding: 20px;
                    &:hover {
                        cursor: pointer;
                        color: $hovercolor;
                    }
                }
            }
            p {
                color: white;
                margin: 0;
            }
        }
    }
</style>