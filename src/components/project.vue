<script setup>
    const props = defineProps({
        title: String,
        des: String,
        languages: Array
    })
</script>

<template>
    <div class="column">
        <div class="box mybox">
            <h1 class="title titleP">{{ title }}</h1>
            <span>Languages: </span>
            <div class="columns langs is-gapless">
                <div v-for="lang in languages" v-bind:key="lang" class="column">
                    <div v-if="lang === 'JS'">
                        <img class="langimage" alt="The Javascript Language logo" style="position: relative; top: 5px;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAYAAABXAvmHAAAABmJLR0QA/wD/AP+gvaeTAAACpklEQVRoge2ZS0hUURjHf8d8Zy8kn2lmZWkYJWUIIkGLwKQWgQ/EjaQJEj0QKi3bFC6LgogIF2Zgj8VUPijUiCAYok2mkAYqNKJiKFY2Ezmnxa0OozM1k3rvovODy/3O+c7j+3Mu53VBo9ForET4csg+pJmB/A2R4T3WILMDWWy0AKvRAqxGC7AaLcBqtACr0QKsRguwmiUTIDLE7+f+E0/f2wEoqRHE5wlCMgWJewVlpwW97wPvx/QR6LbD7kJBSzuMTsD3WRgZh+bHkF0o6LYH1p6pAtxuOHJe4HQZ6bBQSE813gAzTqi9LJABnAVNFdAzAIMffnYcBK/uSfpaJf0dko1JcLwMOhslwudBdz7BSxOqd6amlR0aAls2GHZyPPQ8lESEB96mqSOQmqRspwuKTgmGR4z0vwQPJgtIioP9uSpt64KtBwQV9YKB4X9r0/RZqPGiZGe6SjtdcOsBpBcYQr58Daw90wUkxMCLZkltJURFqvzZWUNITolgctp3/blYshIvj4BLJyRDnZKGk5LYaOXr6YcL1/yfhpZEgNv9Z/+veT56NZypgHftkj3bld/W5X9fCxYwPAKHqgVtz1XeoMOzTESYsm8/guwiwecZlbdqBRTnq9Vr7KP//S9oHbjbAeV1ghknPH0pqCqCtBTJnVbPTyAl0XiX1BhbCICD1YKmBsm6OJj6BLYuVScx1iQBc2eTK00w975483rYtsmwc3ZIWtoN/zM7JO8TJMTAxCS4vqk6xfn+x7CgTygtBdpuSFZGefeHhsD1erU1OFYK56qUX0pwjHkGn7cL6o76vxlalOv10QlouCmwdYFjHNaugdwsOFspycqYX97+Bq42C173wpADIsMhMw1KCyTlhyF4mZdAfVyv6/8DVqMFaDQazf/ND8ttt3KFrySDAAAAAElFTkSuQmCC"/>
                    </div>
                    <div v-else-if="lang === 'Rust'">
                        <img class="langimage" alt="The Rust Language logo" style="position: relative; top: 5px;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAAABmJLR0QA/wD/AP+gvaeTAAAD/UlEQVRIiY2VXWgcVRTHf3e+djNjMrOzH7EPulnFCrZVtG0QlKYgKmpQBMW2KiItxSIiilJFBPGhL6LvCn5AEdEHLYitSMUSxT5oggrVPAjabjclzBKTZju52Z2Z68PO1snHxv5hmHvPmfmfc+459xzYGAPp+xXgVuD1SqVyslAo7CuXy8cBhoaG/I0IxP8YOAOcAA4CMWCPjIxYSikFIKWcsixra71ezwMakFypge+BBvAIoGfkb1YqlXHHcW7LfiylrAsh3JmZGXc1kb5qPw7cA9wL3Jl69TfwLjABjLmue5OU8nQcx/8IISqapmmGYbiAnsvlttm2vTUMw1P9juRZQKXPReAZwMzoD5RKpbd7m3K5fFWlUjlWrVaTWq2marWaKpfLn2YJReZ9CqimzwxwN/B7P0+yKBQKewYHBz/WdV2LoihKkqTVaDQKAEb6jUpJd6V7H/hhPbJqter11lEUXWq32x8FQfCcECIeGhr6zDAMQ0p5MRtBHpgEbmRtTtagVqutkbVarS+DIHhweHj4tG3bt6fGlxcXF6/WAAkcT6M4BiwBJ4HOKp4pYLLdbodJkqiswrbtcUDTdX2LlHIWoN1u/zY/Pz8vgMPAa0AAjNKt/dGUsJjhMYEIwHXd633f/7OniOM4abVa+xzHObqwsLDF87xpIYQIw/BrA/gGeBW4DvgJOAKcX+d0jgDJ8PDwXYZh3NATKqUIw/A94ES73f7R87xpXde1JElUFEVHDeAB/msJ+4Hv1iEHeDk9jhXCMAwnms3moXS72/f9F1zXfUcIIUzT3K+tIjHojylgMoqiKCu0bXuX7/uPAbiuu900zb0ZdaIBX9FNLMC1GxgYBXbU63VzaWlpuicUQmBZ1mEA0zQP2La9E0AppTqdzoc68BQwBuSAzen6UeBmVpbtJmC8WCwuxXF8Jp/PP3Q5bMPYlM/nDw4MDOwWQojUAHEc272b/Bbw0gbeX0axWHxe07QPHMdZTLnWRRiGP8/Ozu7U6Cb4PtISvBIEQdAKw3Cin14phWma2zzP87IufALsSdeHgL8AG/g1+7Pv+825ubmLaTQ7gYeFEGeBscHBwb0AUspzFy5cqEL/ZgfwLXALcA3d274GpVJps+M401EUhZZlOQBps7vUaDR80iqCbpsYo5uLHp4GfqFbPf3w+PLy8lkp5RM9gZTyi0aj4ZFOt9VZGgdGgBfTSDS6Pekk3YFzvlQq3SGEqBqGsSOXy5WFEL2KiaSUnyul/mg2m2/0CPuVwQTd9r16ZK7bTaWU5zRNc1PPV6Dfze3NhTVDXymVHfqTlmVt6yV0PWzUGgC2001wQLcpjodhONbpdN43DOPJIAju9zxvjddZ/AvnGnSdAaNqzgAAAABJRU5ErkJggg=="/>
                    </div>
                    <div v-else-if="lang === 'Node'">
                        <img class="langimage" alt="Node.js logo" style="position: relative; top: 5px;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAABmJLR0QA/wD/AP+gvaeTAAACdklEQVRYhe3XT4hNcRQH8M+Y4cViRvKnpGxMlOyIZjGkZGHYSLKxILaWSsnEYsbGJLY27LCRlJVoEs0sJP8SkvzNYBjKf8/i97vdN3fmvXffHW/nW7+699xzvue83znn9zuP/yiGdvThWVx9UdZ0tGAnXqOcWe+wD9Oa5XwlblQ4HMSauAYr5Dew6l86noPj+BUdvBJ2oSWjt1lIRxl/cBoLpuK4DXsxEkl/xEBq5XoWevEt2oxiP2Y06rwbd6TbegmdDdh3RpvE/k7kzIVt0u1+hJ4GHGfREznKkXNrHqMH0aAfpSk4T1DC0ch5P/sxW0jwW2il6ULUlbqzI9HHCvkcLBMKrgWPcVcoxARt+BllrfUiTvKWRXuUf4rvM3FKmq7K9dDEnFfjLRxAvzS3gziPC3ge5V+wpJkB3I7vGzN6rTGYMg7V423LE1EVJIHsEmrmFt4INdSLYdwrQpx3BzZID5xkfcAVHMTinLyFAyDk+AiuR+eVwXzFlmYFME84sNZldBZhB85Ju6EpAXTG55fC+Z/F3Pj9cz3eokX4RPh1SzGEs0L7lbAQ26PecBHyvDWwAk+Nz3vleiyckDV5JzuKy1W+tUfnY+iIshnYhNWYLxy1b3ETl4UrvB7vBLyPyl2TBJDtgrxYIx3b6mJAOoCcECqetLBGG3A8VxhivkfbgTxGJZyUXjJjwnV6Rjrz1cMsHBBuzeS+OKnB6305LhpfWN+wvoZNK3bjRYXNxchVGF04JuxCQjRzEr0eYQ5IHA9h7VQcV8NSYcy6Jtz53bhqfPttl6Pai2KP0GrZvh8R/pg0PAEXQTsOC6fhw/jcUdPiP6rgLwuk6VCN0aWxAAAAAElFTkSuQmCC"/>
                    </div>
                    <div v-else-if="lang === 'Python'">
                        <img class="langimage" alt="The Python logo" style="position: relative; top: 5px;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAYAAABXAvmHAAAABmJLR0QA/wD/AP+gvaeTAAAD8UlEQVRoge2YTWhcVRSAv3MnaSY/SqlSNEVTartppBZN8Ye2aYwTNUh3jQqCKEoWbqKWtO6yakmoNOBWFF0EaSsFu3CKiROjRUu7aaOpolQ0hEhpQQ1pJpP37nExVUnnzcx7uS9DC/NtZjj3/N775t1zBqpUqXJbI/G4UeHg6HaD6VLlMYEtQDPQCPjANYEZFc4ZOOklvx5nYMDGEdm9gP2j20xCRoDWsCaKnlYv8RLvdlx1DZ9wsh441WD8Nd8BD0QxE2SzEd2lqU0fMj6uLikYF+OahcZdwIaV2KrweE12Z5dLfHAsQOW/5Ges0VaLbQEmw9pbeMIlPrgWYPXO/DdJc/ipKQZTv6NyPLwDucMlPkCNq4M8+gzvjG4lJ/OI7ovHZzhiKoANxsoPsXmLgNMjdCvgtGd2qHMYGC6lY/rH+hCOltLRibo+dJlOFmQStYdlT+5kSf/h060oSdAdiHyqE8nXSimWPoGDmc1GdT/oTmAj+dagkgiqR3Us+YV0Zn8LUih6Aon+L/catRdAe8m3CZVO/l+aSNBbbDG4gLfHWlR0BGhYrazySLiGTvT5YkuBBZhafYtK7Ljqrzc+y8XapJnGe4IWgk9ApdspsXD8aa137EYa28pqG+/hQHGBpC+zlojd5QqYN8gLHHn6ip5pWg8aZsO2BAkLC0h624lt0FmGRWUa5X1recgbfPI0AL43DDSVtRZZFyQueI0mMPdGbNB/EuSQr94oQ6lZkFDmqhi+qjuC6ouholitDxIXFKCq6yIcwIi9vvgq73UvhjXQM03r8XJ7mDD9iD4S1g7Ra0HiggJEyWqI/BUyWm9eZrDb028amvH9A8Be4D5KTXreEvkNijqImdkgadBNHFjpTVhV+wYDnZ5matvwvTTIXREziobxLwSKbxb4Yn4u50uUswylLmmGJAlzYtWThwXql6aCFgrfQpev/gjMl/Kmwvd567oulJYYEixHWtpYClooLOB4j69wtozDfIHKRufUyuNh7aFii4E3saDHQrk2q96OeyC90rF0vngKAVj0E2Bm1dIqTRa4BPoRxrZJe/aDUsrB88Bg6i85MPa6wmdFdcozLO2Lb67QNjRFHwF/sPNzC50KGeD6aieyUpx6noBZNirOp3SrzsShqWQBM4i2grkfuBiX00oWkJbduSlpX5hG9ERcTt3+S1OZi9CUPauZNQ9Sm/gb3/b8b++GWwFivyVM65qnGSOT+Mvm+Gmn+Dg+QrI7NwUS7tYuZA5NnHKJD3H8Bhqzr4B+HNHqMshz0jH/h2v42GZfHa/dAWYfwqMILSh3A3Ugc6heQfgF9BwmkWZ24bz04McVu0qVKrcx/wCMzkVJG0VvSgAAAABJRU5ErkJggg=="/>
                    </div>
                    <div v-else-if="lang === 'Vue'">
                        <img class="langimage" alt="The Vue.js logo" style="position: relative; top: 5px;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAYAAABXAvmHAAAABmJLR0QA/wD/AP+gvaeTAAAEzUlEQVRoge1YXW8bRRQ9d9frxknsxKYkhgQS54FCQRVRo9hOQnksqlB/AEJ8SaBKSE7TNqVN4mRoKqACpVQC8UJpQZQHxEMFRe0bD5VwxYdUECKiLQhI2xhK4jhRnPpjd3iwLDnxzuz6oxISPm+7586998zMzhwbqKOOOuqo4/8MKn549dLRC+DYKQr+7eICbl5eMeVUTeFtj7ge/Wj0xI+ygs+8Obzt75/WLutZg8z4zu0t6B7wihNwfDk1MPFk4VFZzyn7AGRFY7uCXjibVFNOzxp0e8H4VNY8AKz9o58VNe9sVHFfX4tseEYx+P7iF+sEsNDYzxx4TzRadSq4PyiencTc2pZnj408L+Kfe2Pfi0vX0wER3z3ohepURDQ48HZ0KPpL8buS6E05lQG4JUri39oMd5tTWCF5M32CMVaSl33FHIkbt4+Dc9OhHn8D7t7SJGwewF8NmuO1jS9LCh1+7HCCiCaEaQgIPO4DkekuwOqtjPtXR/Ldje+vXVw6mVrImHdIQM8OrzAnABCng4f6DiUtBQCAEcy+D9C3omQefwM2P9AoLLb4e+qlPTMjHYXnPTMjHYk/154Wxbc/6EZz+yZhPoC+N8LZj80YUwGMmME53wvAfL0BdA/6oGrmM5ZJ6crSov5Z4TmxYHyeSemmtVRNQVe4VdI8DIL+MiNmmJHiNQPAYtNnCPSUiJ/7Lok/YglTjlTCPb2tOx061+Z+SJ7jhvlcBIZ86Oj1yNo4NRWeeEFEij95ACD9FQCrIrqj1wNXi8OU4zrH6o3Uh4n51GlR865WDfduc8s6WOZqbkwWIBXAQuw6QK8LB6uE7iGfcHxyPu1fiWc2i/ieHT6QKtkEREdYP4vLepSvAABvwv0WgKsi/q6eRni7XFZpSuALWI675l10v2OVx1JAZFckzTk/KIsJDPmgKNLPaR1IJQQGJXYhHxWJ7IqkrXJZCgAANhA9S8AFEd/o0+CX7+V16Oz1wOXVhDwB56bC4+ft5LIlIJ+UW/ikVqFPKoazSUXndrnfMRRlvyygGLYFRMPRWU4ouWELyPsk6XkOAOgekPsdgB9nwbErdvuyLSCP3BQA4ang3yq/Ue34HU56id+RoSwBLMSWAT4pDJB5Ght+B4TRfA37KHMFAB7ST1r5JLNZbn+o2cLv4NJkcNzU78hQtgBGzCCDhiHzSRv2uepU0BWSHpsG5xgmImFOEcoWAACTg2MxAJ+I+I0njdUJxQmn2cDEN5X0UpEAAOBq7gAA4X4tnPU27ogVzSH5/WGBigWwfhYn4JiIz9+2PstbmgA23jc+X2kfFQsAAMOTk/okX8Bl5XeutiY8wrvFDqoSwB5mGRBGK89Aw3b8jjRDNYMLOBI7ep4DT5Q57Iup8MTuamtXtQIFWPkkE2S4ohyoRe2aCIiGo7MAWXr3AjjHTDl+R4aaCAAATlkGiU8qQhxKTvgrr1zUTAALsWUCRa3iiKhsvyNDzQQAgBHKfgBAfKMSj0WDY2dqWbOmAvI+SRH9n2Rwg/ZW4ndkqKkAIO+TOLjZLJ+q1O/IUHMBAABVH8V6n7Ts0Ky/j0pwRwSwfhYnQtFJw6vyOzLcmRUAYLhzMwCuAJj1a22274j/FFhsejf7erpci1FHHXWUgX8BcmVo3cljsxQAAAAASUVORK5CYII="/>
                    </div>
                    <div v-else-if="lang === 'Flask'">
                        <img class="langimage" alt="The Flask logo" style="position: relative; top: 5px;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADIAAAAyCAYAAAAeP4ixAAAABmJLR0QA/wD/AP+gvaeTAAADYklEQVRoge3XW4iVVRTA8Z8zo83RGtDuESY5NZao3Wymi5WXXoyyiwldiKKeUkx8KXqIim4QUQ/RhQjC6Epmhi8lRVEkxERUpqUPEVZQmdmYEXayHtae/DzznYsNToH7Dwe+vfbe61vrW5e9D5lMJpPJZDKZzIFCe+F5Iqr44z+yZVi0FZ4X40J0tri3vcn8eNyBJf/CriIzsRrTW1k8Dp9jM17EtBbWfyAiuA4r8R5+whdpzXL8iXv20fAi7XgZf+GsVjbMw048h5uxFQ/hiAZ7JqYXXFaQHY7XCuN1uLtVq+swDrvR12hRG3rwEn5Nxh2Ca/EszscrmFCyd1uJ7EcsrBkPl53CkYZ04H48jXeSbBKm4ijh3GJ0KTe8ljl4u0Y2qjV7m9JQT4dIj15cLFLqUazCcejG901ecG7SMxmHaexIF25Pus/DbSLykuyxtH4KlmJNjZ7TcC/G4issw3YitTaKQqpgBdZjF37GQBMnJKXjcQp2lMwXHVkm6ugqPIVrCnNL8AnmY0FaV8uA+PC34vpBJwbpFd3nXVG4vYW5uQ0cODgpvTSNu3B5zZrXcV/J3tF4BGsLsuuSHS+I6BapJj1ba+z7hzb0i3Q4VnSp70TY5ysv8noM4NUSeTEiU/GM6IjHiPY8yApcgBOxQUStyCR8hAeUnGFtSdna5ESPyNPtIkKbRPsro1Lfp72caC88vyVa8lK8b28nFyTZTFE3VxZsHIUncANmiA9RysniK6zHTcL7McnY2SXrR+MukVprcFHJmm5swZf2pNzH4uB9WDSUXXg8zfWLY2C5OFwXJfmN6T3PizqcJ65RK8VNZAgPpg0b8WYysB13Gtr6OnA6TsCpOKlE3/HppWeKlCLOqDk4Oo0nF3RXks7ZhXlJ/xlpblA+A+eIchhCt/gSX+NqfCZqpVOdAvs/USyabel3iTC8Ilrgahwp+vw3I21gq9RW/2Zxmk8Xra5H9Os3RDeZhk9H0sDhUMEt+Ba/CIf6cahoCgtFfg7Sh1kjbOMQyv5TVPGhuKiNsSetZokiHyuK72xcIQ7RHSJ6feJ82LS/Da+l2YVugojCXFE3U/CbuFPtFl2kit9F+/5BdLsn95O9ddmXm2mnaJdVEalOHCRSb4u4bmcymUwmk8lkMpnMAcff/Aemjy3IAsMAAAAASUVORK5CYII="/>
                    </div>
                    <div v-else-if="lang === 'Postgres'">
                        <img class="langimage" alt="The PostgresSQL logo" style="position: relative; top: 5px;" src="data:image/png;base64,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"/>
                    </div>
                </div>
            </div>
            <p class="description">
                {{ des }}
            </p>
        </div>
    </div>
</template>

<style scoped>
.langs {
    display: inline-flex;
}
.mybox {
    height: 100%;
    font-family: 'Source Sans Pro', sans-serif;
    z-index: 1;
}
.langimage {
    height: 30px;
    width: 30px;
}
.titleP {
    background: radial-gradient(circle, rgba(63,94,251,1) 0%, rgba(252,70,107,1) 100%);
    font-family: 'Source Sans Pro', sans-serif;
    font-weight: bold;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
    padding: 0;
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
  
}

/* 
  ##Device = Most of the Smartphones Mobiles (Portrait)
  ##Screen = B/w 320px to 479px
*/

@media (min-width: 320px) and (max-width: 480px) {
    .mybox {
        padding-bottom: 40px;
    }
}
</style>