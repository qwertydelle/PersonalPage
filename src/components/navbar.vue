<script setup>
    import {ref,  getCurrentInstance} from "vue"
    const emit = defineEmits()

    function mousemove() {
        emit("mouse");
    }

    function scrollTo(id){
        document.getElementById(id).scrollIntoView({behavior: "smooth", block: "end", inline: "nearest"})
    }
</script>
<template>
    <div class="navbar decnav" id="start" role="navigation" >
        <div class="navbar-brand">
            <div class="navbar-item">
                <svg id="logo-svg" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:svgjs="http://svgjs.dev/svgjs" version="1.1" width="90%" height="80%" viewBox="0 0 1000 600"><rect id="logo-rect" width="600" height="600" x="0" y="0"/><g><circle r="166.66666666666666" cx="291.0686594645182" cy="313.29091404443864" fill="#1098f7" transform="matrix(1.0048067464330137,0,0,1.0048067464330135,0,-14.796822658658272)"/><path d="M338.5680861795572 388.29092392885696L243.56924687799471 388.29092392885696L243.56924687799471 238.29092446002855L338.5680861795572 238.29092446002855L338.5680861795572 388.29092392885696ZM254.09953228976556 248.80380444136674L254.09953228976556 377.76063851708614L328.03780076778634 377.76063851708614L328.03780076778634 248.80380444136674L254.09953228976556 248.80380444136674Z " fill="#ffffff" transform="matrix(1.0048067464330137,0,0,1.0048067464330135,0,-14.796822658658272)"/><path d="M870.8142452524572 268.5257633230816L541.0686672558687 268.5257633230816L541.0686672558687 238.29093139401755L870.8142452524572 238.29093139401755L870.8142452524572 268.5257633230816ZM870.8142452524572 388.2909228090829L541.0686672558687 388.2909228090829L541.0686672558687 358.0560908800188L870.8142452524572 358.0560908800188L870.8142452524572 388.2909228090829Z " fill="#791e94" transform="matrix(1.0048067464330137,0,0,1.0048067464330135,0,-14.796822658658272)"/></g></svg>
            </div>
        </div>
        <div class="navbar-menu">
            <div class="navbar-end">
                    <a class="navbar-item declink" @mouseenter="mousemove" @mouseleave="mousemove" @mousedown="scrollTo('start')">Home</a>
                    <a class="navbar-item declink" @mouseenter="mousemove" @mouseleave="mousemove" @mousedown="scrollTo('about')">About</a>
                    <a class="navbar-item declink" @mouseenter="mousemove" @mouseleave="mousemove" @mousedown="scrollTo('projects')">Projects</a>
                    <a class="navbar-item declink" @mouseenter="mousemove" @mouseleave="mousemove" @mousedown="scrollTo('contact')">Contact</a>
            </div>
        </div>
    </div>
</template>
<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Josefin+Sans&display=swap');

    .decnav {
        scroll-snap-align: start;
        height: 15%;
        cursor: none;
        background-color: var(--main-bg-color);
        position: relative;
        z-index: -1;
    }

    #logo-rect {
        fill: var(--main-bg-color);
    }

    #logo-svg {
        width: 90%;
        height: 80%;
    }

    .declink {
        font-size: 20px;
        font-family: 'Josefin-Sans', sans-serif;
        margin-right: 20px; 
        margin-bottom: 25px;
        cursor: none;
        color: var(--main-accent-color);
    }
    .navbar-item:hover {
        background-color: transparent !important;
        color: #1098F7;
        cursor: none;
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
  
  /* CSS */
    #logo-svg {
        width: 50%;
    }
}

/* 
  ##Device = Most of the Smartphones Mobiles (Portrait)
  ##Screen = B/w 320px to 479px
*/

@media (min-width: 320px) and (max-width: 480px) {
  
    #logo-svg {
        width: 50%;
    }
}
</style>W

