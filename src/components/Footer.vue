<template>
    <div id="footer">
        <div class="overlay">
            <div class="icon-holder">
                <a href="https://www.github.com/ekwon86" target="_blank">
                    <i class="fa fa-2x fa-github contact-icons" aria-hidden="true"></i>
                </a>
                <a href="https://www.linkedin.com/in/eugene-kwon-01843836/" target="_blank">
                    <i class="fa fa-2x fa-linkedin contact-icons" aria-hidden="true"></i>
                </a>
                <a href="https://angel.co/eugene-kwon" target="_blank">
                    <i class="fa fa-2x fa-angellist contact-icons" aria-hidden="true"></i>
                </a>
                <a href="mailto:ekwon86@gmail.com" target="_blank">
                    <i class="fa fa-2x fa-envelope contact-icons" aria-hidden="true"></i>
                </a>
                <i class="fa fa-2x fa-file-pdf-o contact-icons" aria-hidden="true"></i>
            </div>
            <p>&copy; {{ currentYear }} Eugene Kwon</p>
        </div>
    </div>
</template>

<script>
    export default{
        data(){
            return {
                currentYear: ''
            }
        },
        methods: {
            getCurrentYear() {
                this.currentYear = new Date().getFullYear();
            }
        },
        mounted() {
            this.getCurrentYear();
        }
    }
</script>

<style lang="scss" scoped>
    $hovercolor: #32a8d0;
    #footer {
        width: 100%;
        min-height: 100px;
        height: auto;
        text-align: center;
        background-position: bottom;
        background-repeat: no-repeat;
        background-size: cover;
        background-attachment: fixed;
        .overlay {
            height: 100%;
            position: relative;
            width: 100%;
            background-color: rgba(53, 53, 53, 0.3);
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
    @media (min-width: 320px) and (max-width: 480px) {
        #footer .overlay {
            padding: 12px;
            background-color: rgba(0,0,0,0.9);
        }
        .contact-icons {
            font-size: 20px;
        }
        p {
            font-size: 12px;
        }
    }
</style>
