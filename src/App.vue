<script setup>
  import navig from "./components/navbar.vue"
  import Home from "./sections/home.vue"
  import About from "./sections/about.vue"
  import Project from "./sections/projects.vue"
  import Contact from "./sections/contact.vue"
  import Footy from "./components/footer.vue"
  import { ref, reactive } from "vue"
  import { resolveComponentType } from "@vue/compiler-core";

  const emits = defineEmits(["mouse"])

  let top = ref(0)
  let left = ref(0)
  let ui = ref(true)
  let mouseWidth = ref(30);
  let mouseHeight = ref(30);

  function mousemove(event) {
    let mouseX = event.clientX
    let mouseY = event.clientY
    top.value = mouseY
    left.value = mouseX
  }

  if(localStorage.getItem("mode")) {
    if(localStorage.getItem("mode") === "light") {
      ui.value = false
      updateUi()
    }else {
      ui.value = true
      updateUi()
    }
  }

  function updateUi() {
    let root = document.querySelector(":root")


    if(ui.value) {
      root.style.setProperty("--main-bg-color", "#1a1a1a" )
      root.style.setProperty("--main-accent-color", "#F3F3F3")
      root.style.setProperty("--main-tone-color", "#FFFFFF")
      root.style.setProperty("--main-blob-color", "#1098F7")
      root.style.setProperty("--main-mouse-color", "#791E94")

      ui.value = false
      localStorage.setItem("mode", "dark")
    } else {
      root.style.setProperty("--main-bg-color", "#FFFFFF" )
      root.style.setProperty("--main-accent-color", "#000000")
      root.style.setProperty("--main-tone-color", "grey")
      root.style.setProperty("--main-blob-color", "#791E94")
      root.style.setProperty("--main-mouse-color", "#1098F7")

      ui.value = true
      localStorage.setItem("mode", "light")
    }
  }

  function mouseClick(event) {
    if(event.type === "mouseup") {
      mouseWidth.value = 30
      mouseHeight.value = 30

    } else {
      mouseWidth.value = 20
      mouseHeight.value = 20
    }
  }
</script>

<template>
    <div class="blob" @mousemove="mousemove" @mousedown="mouseClick" @mouseup="mouseClick">
            <!-- This SVG is from https://codepen.io/Ali_Farooq_/pen/gKOJqx -->
           <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
  <path d="M34.5,-59.5C46.1,-52.9,58.1,-46.7,69,-36.8C79.9,-27,89.8,-13.5,89.5,-0.2C89.2,13.1,78.7,26.3,70.1,40.1C61.4,53.9,54.6,68.4,43.3,73.4C31.9,78.4,16,74,0.4,73.3C-15.2,72.6,-30.3,75.7,-40.4,69.9C-50.4,64.1,-55.4,49.5,-58.3,36.3C-61.2,23.2,-62,11.6,-65.5,-2C-68.9,-15.6,-74.9,-31.1,-72.5,-45.2C-70.1,-59.2,-59.4,-71.7,-45.9,-77.2C-32.4,-82.7,-16.2,-81.1,-2.4,-76.9C11.4,-72.8,22.8,-66,34.5,-59.5Z" transform="translate(100 100)" />
</svg>
            </div>
  <div id="realbody" @mousemove="mousemove" @mousedown="mouseClick" @mouseup="mouseClick">
    <div id="mouse" v-bind:style="{top: top + 'px', left: left + 'px', width: mouseWidth + 'px', height: mouseHeight + 'px'}"></div>
    <navig></navig>
    <Home></Home>
    <About></About>
    <Project></Project>
    <Contact></Contact>
    <Footy></Footy>
    <div id="moon">
      <svg width="50" height="44" stroke-width="1.5" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" @mousedown="updateUi">
<path d="M3 11.5066C3 16.7497 7.25034 21 12.4934 21C16.2209 21 19.4466 18.8518 21 15.7259C12.4934 15.7259 8.27411 11.5066 8.27411 3C5.14821 4.55344 3 7.77915 3 11.5066Z" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"/>
</svg>
    </div>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@400;700&display=swap');

html, body {
  height: 100%;
  cursor: none;
  scroll-behavior: smooth;
}

:root {
  --main-bg-color: #FFFFFF;
  --main-accent-color: #000000;
  --main-scroll-color: #1098F7;
  --main-tone-color: grey;
  --main-blob-color: #791E94;
  --main-mouse-color: #1098F7;
}

::-webkit-scrollbar {
  width: 5px;
  display: none;
}

::-webkit-scrollbar-track {
  background-color: var(--main-bg-color);
}

::-webkit-scrollbar-thumb {
  background: var(--main-scroll-color);
  border-radius: 20px;
  margin: 1px;
}

::selection {
  color: #FFFFFF;
  background-color: #791E94;
}

::moz-selection {
  color: #FFFFFF;
  background-color: #791E94;
}

#mouse {
  position: fixed;
  border: 2px solid var(--main-mouse-color);
  border-radius: 50%;
  height: 30px;
  width: 30px;
  z-index: 31;
  transition: height 0.1s, width 0.1s;
}


#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height: 100%;
  background-color: var(--main-bg-color);
}

#realbody {
  scroll-snap-type: y mandatory;
  height: 100%;
  min-height: 100%;
  overflow: auto;
  z-index: 1;
  position: relative;
}

#moon {
  position: fixed;
  bottom: 0;
  margin: 10px;
}


#moon, svg {
  padding-top: 2px;
  color: var(--main-blob-color);
}

@import url('https://fonts.googleapis.com/css?family=Poppins:700');


h1 {
  color: white;
  font-size: 20vmin;
  line-height: 1;
  font-weight: bold;
  letter-spacing: 2px;
  font-family: 'Poppins', sans-serif;
  text-transform: uppercase;
  padding-left: 40px;
}

.blob {
  position: fixed;
  top: 0;
  left: 0;
  fill: var(--main-blob-color);
  width: 50vmax;
  z-index: 0;
  animation: move 50s ease-in-out infinite;
  transform-origin: 60% 50%;
  transition: transform 1s;
  transform: scale(0.8, 1) translate(80vw, 30vh) rotate(160deg);
}

.blob path {
  fill: var(--main-blob-color);
}

/* @keyframes move {
  0%   { transform: scale(2)   translate(10px, 0px); }
  38%  { transform: scale(0.8, 1) translate(80vw, 30vh) rotate(160deg); }
  40%  { transform: scale(0.8, 1) translate(80vw, 30vh) rotate(160deg); }
  78%  { transform: scale(1.3) translate(0vw, 50vh) rotate(-20deg); }
  80%  { transform: scale(1.3) translate(0vw, 50vh) rotate(-20deg); }
  100% { transform: scale(2)   translate(10px, 0px); }
} */

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
    #mouse {
      display: none;
    }

    .blob {
      display: none;
    }
  
}

/* 
  ##Device = Tablets, Ipads (landscape)
  ##Screen = B/w 768px to 1024px
*/

@media (min-width: 768px) and (max-width: 1024px) and (orientation: landscape) {
  
  /* CSS */
    #mouse {
      display: none;
    }

    .blob {
      display: none;
    }
  
}

/* 
  ##Device = Low Resolution Tablets, Mobiles (Landscape)
  ##Screen = B/w 481px to 767px
*/

@media (min-width: 481px) and (max-width: 767px) {
  
  /* CSS */
    #mouse {
      display: none;
    }

    .blob {
      display: none;
    }
}

/* 
  ##Device = Most of the Smartphones Mobiles (Portrait)
  ##Screen = B/w 320px to 479px
*/

@media (min-width: 320px) and (max-width: 480px) {
    #mouse {
      display: none;
    }

    .blob {
      display: none;
    }


}
</style>
