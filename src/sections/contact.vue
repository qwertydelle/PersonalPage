<script setup>
    import { ref}  from "vue"

    let message = ref("")

    function sendMail() {
        window.location.href = `mailto:lit.cloting@gmail.com?subject=Website&body=${message.value}`
    }
</script>

<template>
    <div id="contact">
        <h1 id="title">Contact</h1>
        <div class="field">
            <div class="columns">
                <div class="column is-half con">
                    <textarea class="textarea is-medium" placeholder="Message..." rows="10" v-model="message"></textarea>
                    <br>
                    <button class="button mybutton" @click="sendMail">Submit</button>
                </div>
                <div class="column is-half con">
                    <div class="box">
                        <h5 id="littlesnip">Socials</h5>
                        <div class="quick">
                            <img  alt="Github Icon" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAB4AAAAeCAYAAAA7MK6iAAAABmJLR0QA/wD/AP+gvaeTAAAB0ElEQVRIie3WPWtUQRTG8V8SMEE7C41JDBK1tVZBIgo2QhJBrW0sFNQirZXfQiW+oJUQMJhgI/gJbKy0E7QLRFzBl5i4Fvdec507921XUuWByzJzz3P+58zO7Cw72iYNtIidxCzO4xAm0vlP+IBlLOHj/ypuHHexgW7Ns4lnaWF9aQ5fGwDDp4OZXqG3JB20hea7v9kWOtcnNA9v3PmE4vIexzEs1IAW0riTubkOxpqAY8mHg9WYxj4MpZ+n0/lMI4H/fh10Unz3HmlScU5HA/+GreMHBgPDbNpFqP0twaPBeCjNXaqXit0utoRmWgryrFQFv4+AT/QIPhXkeVcV3ImAh6sMFdoT5OnkX4bfcTjWB3gkGP+zd0LQaiTBdI/g0BfL/Vcrikv9RrH6Ou3G2yDPiyrDfATcxSsNf30k5/V1JMd8lekg1kvg3/AAlzAV+KZwGY/wPeJdx4G6ip/kDFfwPFLAucBzBj9KCu7icR2U5OJfSw2r2IunaeLPuF3iu1MC/aJBt5ku2roWrzb0HI5AN3GhKTTTdfyW/Kc6q35nD0ag19pCM81IljefsEpZzJoeOg01hnv41QD8Ew8Vb6e+NIob2FXyfkDzs76j7dMfXTjhKzmestYAAAAASUVORK5CYII="/>
                            <a class="slashlink" href="https://github.com/qwertydelle">/qwertydelle</a>
                        </div>
                        <br>
                        <div class="quick">
                            <img alt="Twitter Icon" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAB4AAAAeCAYAAAA7MK6iAAAABmJLR0QA/wD/AP+gvaeTAAABjElEQVRIie3Wv0vVURjH8ZdKEojYD9ocHTTE1RYTIxAy3ARRaBcM+hfEWaJoaysaxEGJWhpadBSHEBx0KYWWCkJIM38N537hcvvec7/n3tuSfuDZzvm8z/OcH8/hUv+7WprkcxUPMYAzfMJ7HFaMa8dRnsFtXEuEjmC3BCyPzxjGDUzjAzqrmbzCamxAhe7gIAeaxRGOcYopkQpvliaso7sAeCMCzeIUy1jA42pG22UTvmEyAu0rAC2PJbRVM1vJmbCKB/4u03gC9CVaI0lEzb7gGSZK2Y4lgCdiULiC1wmGRWO4ElSZ/oZwGL7XWmGivtYa8E7zs90XHo6oRv8B+G0taKb5JoNnioLhEfaaAP2hyiuYd7daMYQt/E5ZbY6eC3tcWE80nu0erqeutAUvGoCe4F4qtFz3hVOZ1/ZiMdcINFMv1hKgTzXwwegQ7vQi/hQEHoq0vZiGhO/KjtDAU0r7Ef31QDN1YVb4CNSC/cQb3K0HFNuLWxhED24KneuXcE02hYZyXA/0UhdD5+q+K5z2ztKIAAAAAElFTkSuQmCC"/>
                            <a class="slashlink" href="https://twitter.com/undefined">/tobeheresoon</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.con {
    margin-left: 70px;
    padding-top: 10%;
    padding-bottom: 10%;
}

#contact {
    scroll-snap-align: start;
    height: 100%;
    min-height: 100%;
    z-index: 1;
}

textarea {
    cursor: none;
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

#littlesnip {
    background: -webkit-linear-gradient(270deg,#F72C25 10%,#1098F7);
    font-family: 'Source Sans Pro', sans-serif;
    font-weight: bold;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
    padding-bottom: 20px;
}

.quick {
    display: flex;
}

.slashlink {
    padding-left: 10px;
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
    
    #contact {
        overflow: hidden;
        height: fit-content;
    }

    .con {
        margin: 10px;
    }

    .mybutton {
        width: 100%;
        border-color: var(--main-mouse-color);
    }
    textarea {
        width: 50%;
        resize: both;
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
   #contact {
        overflow: hidden;
        height: fit-content;
    }

    .con {
        margin: 10px;
    }

    .mybutton {
        width: 100%;
        border-color: var(--main-mouse-color);
    }
    textarea {
        width: 50%;
        resize: both;
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
    
    #contact {
        overflow: hidden;
        height: fit-content;
    }

    .con {
        margin: 10px;
    }

    .mybutton {
        width: 100%;
        border-color: var(--main-mouse-color);
    }
    textarea {
        width: 50%;
        resize: both;
    }

}
</style>