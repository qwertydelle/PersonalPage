<script setup>
import project from "../components/project.vue"

let langs = ['JS', 'Rust']
</script>

<template>
    <div id="projects">
        <h1 id="title">Projects</h1>
        <div class="columns container">
            <project title="Duxty" :languages="['JS', 'Node']" des="Duxty is a command line tool that makes it easy to setup discord bots. Duxty was built with Javascript."></project>
            <project title="Websitespot" :languages="['Python', 'Vue', 'Flask', 'Postgres']" des="This was a website I made using Vue, Flask and Python. "></project>
            <project title="Cord.js" :languages="['JS', 'Node']" des="Javascript Discord Library that I built just for fun during covid."></project>
            <project title="Snake" :languages="['Rust']" des="A snake game I made with Rust and GGEZ. This game was made in order to help me get better at writing Rust."></project>
        </div>
    </div>
</template>

<style scoped>
#bottom {
    text-align: center;
    color: var(--main-tone-color);
}

#bottom, a:hover {
    color: var(--main-tone-color);
}

#bottom a {
    text-decoration: underline; 
    color: var(--main-tone-color);
}
.container {
    margin: auto;
    margin-top: 5%;
    height: 40%;
}
#projects {
    scroll-snap-align: start;
    height: 100%;
    min-height: 100%;
    z-index: 1;
}

#title {
    padding-top: 40px;
    text-align: center;
    font-size: 100px;
    background: -webkit-linear-gradient(270deg,#F72C25 10%,#1098F7);
    font-family: 'Source Sans Pro', sans-serif;
    font-weight: bold;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
}



/* 
  ##Device = Desktops
  ##Screen = 1281px to higher resolution desktops
*/

@media (min-width: 1281px) {
  
  /* CSS */
  
}

/* 
  ##Device = Laptops, Desktops
  ##Screen = B/w 1025px to 1280px
*/

@media (min-width: 1025px) and (max-width: 1280px) {
  
  /* CSS */
  
}

/* 
  ##Device = Tablets, Ipads (portrait)
  ##Screen = B/w 768px to 1024px
*/

@media (min-width: 768px) and (max-width: 1024px) {
  
  /* CSS */
    #projects {
        font-size: 20px;
        overflow: hidden;
        height: fit-content;
    }
  
}

/* 
  ##Device = Tablets, Ipads (landscape)
  ##Screen = B/w 768px to 1024px
*/

@media (min-width: 768px) and (max-width: 1024px) and (orientation: landscape) {
  
  /* CSS */
  
}

/* 
  ##Device = Low Resolution Tablets, Mobiles (Landscape)
  ##Screen = B/w 481px to 767px
*/

@media (min-width: 481px) and (max-width: 767px) {

  #title {
        font-size: 40px;
        padding-left: 0;
    }
  
  /* CSS */
  #projects {
        font-size: 20px;
        overflow: hidden;
        height: fit-content;
    }
}

/* 
  ##Device = Most of the Smartphones Mobiles (Portrait)
  ##Screen = B/w 320px to 479px
*/

@media (min-width: 320px) and (max-width: 480px) {
  
    #title {
        font-size: 40px;
        padding-left: 0;
    }
    
    #projects {
        font-size: 20px;
        overflow: hidden;
        height: fit-content;
    }

}
</style>
