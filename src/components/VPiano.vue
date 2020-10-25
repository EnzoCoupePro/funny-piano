<template>
    <div class="piano">
        <div class="touche">
            <div class="blanche" id="c" @click.prevent="playSound('/assets/sounds/C.mp3')" @click="getGifs()"></div>
            <div class="noir" id="cs" @click.prevent="playSound('/assets/sounds/C%23.mp3')" @click="getGifs()">
                <span></span>
            </div>
            <div class="blanche" id="d" @click.prevent="playSound('/assets/sounds/D.mp3')" @click="getGifs()"></div>
            <div class="noir" id="ds" @click.prevent="playSound('/assets/sounds/D%23.mp3')" @click="getGifs()">
                <span></span>
            </div>
            <div class="blanche" id="e" @click.prevent="playSound('/assets/sounds/E.mp3')" @click="getGifs()"></div>
            <div class="blanche" id="f" @click.prevent="playSound('/assets/sounds/F.mp3')" @click="getGifs()"></div>
            <div class="noir" id="fs" @click.prevent="playSound('/assets/sounds/F%23.mp3')" @click="getGifs()">
                <span></span>
            </div>
            <div class="blanche" id="g" @click.prevent="playSound('/assets/sounds/G.mp3')" @click="getGifs()"></div>
            <div class="noir" id="gs" @click.prevent="playSound('/assets/sounds/G%23.mp3')" @click="getGifs()">
                <span></span>
            </div>
            <div class="blanche" id="a" @click.prevent="playSound('/assets/sounds/A.mp3')" @click="getGifs()"></div>
            <div class="noir" id="as" @click.prevent="playSound('/assets/sounds/A%23.mp3')" @click="getGifs()">
                <span></span>
            </div>
            <div class="blanche" id="b" @click.prevent="playSound('/assets/sounds/B.mp3')" @click="getGifs()"></div>
        </div>
        
    </div>
</template>

<style lang="postcss" scoped>

.piano {
    width: 531px;
    height: 276px;
    margin: 0 auto;
}

.touche {
    display: flex;
    background-color: #000;
    padding: 12px;
    height: 100%;
    position: relative;
    border-radius: 10px;

}

.blanche {
    /** 
        flex: 1; permet de dire que la largeur de chaque .blanche est identique
    */
    flex: 1; 
    background-color: white;
    margin-left: 2px;
    margin-right: 2px;
}

.noir {
    position: relative;
}

.noir span {
    width: 30px;
    height: 80%;
    /* translateX(-50%) permet de décaler la touche noir de -50% de sa largeur ; */
    transform: translateX(-50%); 
    top: 0;
    display: block;
    position: absolute;
    background-color: #000;
    border-radius: 0px 0px 5px 5px;
}

#c{
    border-radius: 5px 0px 0px 5px;
}

#b{
    border-radius: 0px 5px 5px 0px;
}
.blanche:active {
  background-color: #ffd12d;
}

.noir span:active {
  background-color: #E6016F;
}


@media (max-width:650px){
    .piano {
        width: 368px;
        height: 190px;
    }
    .touche {
        padding: 8px;
    }
    .noir span {
        width: 21px;
    }
}
</style>
 
<script>
import { GiphyFetch } from '@giphy/js-fetch-api'
export default {
    data(){
        return {
            gifs:[]
        }
    },
    methods: {
        playSound: function (url){
            new Audio(url).play();
        },
        async getGifs() {
            const gf = new GiphyFetch('hoc7Xw81iwUP2iewXhekupQznVmYDlHK')
            const { data: gifs } =  await gf.emoji()
            const nbRandom = Math.floor(Math.random() * Math.floor(10));
            const urlRandom = gifs[nbRandom].images['fixed_width'].webp;

            document.getElementById('emoji').src=urlRandom;
        },
    }   
}
</script>