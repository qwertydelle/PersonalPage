<script setup>
</script>

<template>
    <div class="whole">
       <h1 id="name">Declan<br><span>Software Engineer</span></h1>
       <div class="scrollMouse">
       </div>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@400;700&display=swap');
.whole {
    margin: 30px;
    text-align: center;
    height: 100%;
    z-index: 1;
}

#name {
    padding-top: 40px;
    font-size: 100px;
    background: -webkit-linear-gradient(320deg,#F72C25 15%,#1098F7);
    font-family: 'Source Sans Pro', sans-serif;
    background-clip: text;
    font-weight: bold;
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
}

.scrollMouse {
    width: 50px;
    height: 80px;
    background-color: transparent;
    margin: auto;
    border-radius: 30px;
    border: 1px solid var(--main-accent-color);
    margin-top: 60px;
    position: relative;
}

.scrollMouse::after {
    content: "";
    position: absolute;
    width: 2px;
    top: 10px;
    border-radius: 50%;
    height: 15px;
    background-color: var(--main-accent-color);
    animation: move 1s infinite;
}


@keyframes move {
    from {
        top: 10px;
    }

    to {
        top: 30px;
        opacity: 0;
    }
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
   #name {
        font-size: 70px;
        padding-top: 40%;
        padding-left: 0;
    }

    .scrollMouse {
        width: 0;
        height: 0;
    }
  
}

/* 
  ##Device = Tablets, Ipads (landscape)
  ##Screen = B/w 768px to 1024px
*/

@media (min-width: 768px) and (max-width: 1024px) and (orientation: landscape) {
  
  /* CSS */
   #name {
        font-size: 70px;
        padding-top: 50%;
        padding-left: 0;
    }

    .scrollMouse {
        width: 0;
        height: 0;
    }
  
}

/* 
  ##Device = Low Resolution Tablets, Mobiles (Landscape)
  ##Screen = B/w 481px to 767px
*/

@media (min-width: 481px) and (max-width: 767px) {
  
  /* CSS */
   #name {
        font-size: 40px;
        padding-top: 20%;
        padding-left: 0;
    }

    .scrollMouse {
        width: 0;
        height: 0;
    }
  
}

/* 
  ##Device = Most of the Smartphones Mobiles (Portrait)
  ##Screen = B/w 320px to 479px
*/

@media (min-width: 320px) and (max-width: 480px) {
  
    #name {
        font-size: 40px;
        padding-top: 50%;
        padding-left: 0;
    }

    .scrollMouse {
        width: 0;
        height: 0;
    }
    

}
</style>