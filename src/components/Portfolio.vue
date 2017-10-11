<template>
    <div id="Portfolio">
        <div class="portfolio-content">
          <p class="headings portfolio-heading">Portfolio</p>
          <div class="project-container">
            <div class="indiv-project-subcontainers" v-for="project in lfzProjects" :style="{ 'background': 'url(' + project.imgPath + ')' }">
              <h3>{{ project.name }}</h3>
            </div>
          </div>
        </div>
    </div>
</template>

<script>
    export default{
        data(){
            return {
              lfzProjects: [
                {
                  name: 'Mega Match Man',
                  url: 'http://www.eugenekwon.com/projects/megamatchman',
                  imgPath: '../assets/megamatchman.png'
                },
                {
                  name: 'Calculator',
                  url: 'http://www.eugenekwon.com/projects/calculator',
                  imgPath: '../assets/calculator.png'
                },
                {
                  name: 'I Want',
                  url: 'http://www.eugenekwon.com/projects/iwant',
                  imgPath: '../assets/iwant.png'
                }
              ],
              workProjects: [
                {
                  name: 'Conference 2017 Site',
                  url: 'http://www.laserapp.com/conference2017'
                }
              ]
            }
        }
    }
</script>

<style lang="scss">
    #Portfolio {
        height: 1500px;
        position: relative;
        width: 100vw;
        background-color: white;
        padding: 5% 15%;
        .portfolio-content {
            position: relative;
            top: 50%;
            width: 100%;
            transform:translateY(-50%);
            height: 100%;
            .portfolio-heading {
              border-bottom: 1px solid rgba(0,0,0,0.1);
            }
        }
    }
    .project-container {
      min-height: 800px;
      font-size: 0;
      height: auto;
      vertical-align: top;
      border: 1px solid black;
    }
    .indiv-project-subcontainers {
      border: 1px solid red;
      padding: 25px;
      width: 33.33%;
      display: inline-block;
      height: 250px;
      background-position: center;
      background-repeat: no-repeat;
      background-size: cover;
      &:hover {
        cursor: pointer;
      }
    }
</style>
