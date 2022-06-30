<script setup>

</script>

<template>
    <div id="about">
        <h1 id="title">About</h1>
        <div class="upper">
            <div class="column content-container">
                <p class="content">Hello, My name is Declan, and I am an aspiring Software Engineer based in Maryland. I specialize in Full Stack Development and work with Tools such as Vue, Node JS, Bulma, Express, Vite, MongoDB, PostgreSQL, etc. I also work with programming languages like Rust, Python, Javascript, Typescript, Lua and Java.</p>
            </div>
        </div>
    </div>
</template>

<style scoped>

#about {
    scroll-snap-align: start;
    height: 100%;
    min-height: 100%;
    z-index: 1;
}
.content-container {
    margin: auto;
    text-align: left;
    width: 60%;
}
.content {
    color: var(--main-accent-color);
    font-family: 'Source Sans Pro', sans-serif;
    font-size: 20px;
    padding-top: 10%;
}
.upper {
    margin: 10px;
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
  .content {
        font-size: 15px;
    }

    #title {
        font-size: 40px;
        padding-left: 0;
    }

    .content-container {
        margin: auto;
        text-align: left;
        width: 100%;
        padding-top: 5%;
        text-align: center;
    }
  
}

/* 
  ##Device = Most of the Smartphones Mobiles (Portrait)
  ##Screen = B/w 320px to 479px
*/

@media (min-width: 320px) and (max-width: 480px) {
    .content {
        font-size: 20px;
    }

    #title {
        font-size: 40px;
        padding-left: 0;
    }

    .content-container {
        margin: auto;
        text-align: left;
        width: 100%;
        padding-top: 20%;
        text-align: center;
    }
}
</style>