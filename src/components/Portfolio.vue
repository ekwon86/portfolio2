<template>
    <div id="Portfolio">
        <div class="portfolio-content">
          <p class="headings portfolio-heading">Portfolio</p>
          <div class="project-container">
            <div class="indiv-project-subcontainers" v-for="project in lfzProjects">
                <div class="indiv-project-img-holder">
                    <div class="indiv-projects-img" :id="project.id"></div>
                </div>
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
                  id: 'megamatchman',
                  url: 'http://www.eugenekwon.com/projects/megamatchman'
                },
                {
                  name: 'Calculator',
                  id: 'calculator',
                  url: 'http://www.eugenekwon.com/projects/calculator'
                },
                {
                  name: 'Tic-Tac-Toe',
                  id: 'tictactoe',
                  url: 'http://www.eugenekwon.com/projects/iwant'
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
      border: 1px solid blue;
      margin-bottom: 10px;
      padding: 10px;
      width: 33.33333%;
      display: inline-block;
      height: 250px;
        #megamatchman {
            background: url(../assets/megamatchman.jpg);
        }
        #calculator {
            background: url(../assets/calculator.jpg);
        }
        #tictactoe {
            background: url(../assets/tictactoe.jpg);
        }
    }
    .indiv-project-img-holder {
        height: 100%;
        width: 100%;
        overflow: hidden;
    }
    .indiv-projects-img {
        width: 100%;
        height: 100%;
        -moz-transition: all .5s ease;
        -webkit-transition: all .5s ease;
        transition: all .5s ease;
        background-size: 100% 100% !important;
        background-position: center !important;
    }
    .indiv-projects-img:hover {
        cursor: pointer;
        -moz-transform: scale(1.15);
        -webkit-transform: scale(1.15);
        -o-transform: scale(1.15);
        -ms-transform: scale(1.15);
    }
</style>
