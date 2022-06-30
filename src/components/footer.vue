<script setup>

</script>
<template>
    <div id="footer">
        <footer class="footer">
             <div class="content has-text-centered">
                 <a href="https://icons8.com/">All icons used provided by Icons8</a>
                 <p>Version: <b>3.0.0</b></p>
                <div>
                    <p id="bottom">More projects on my github: <a  href="https://github.com/qwertydelle">https://github.com/qwertydelle</a></p>
                </div>
             </div>
        </footer>
    </div>
</template>
<style scoped>
#footer {
    scroll-snap-align: start;
    z-index: 1;
}

#bottom a {
    text-decoration: underline; 
    color: black;
}
</style>