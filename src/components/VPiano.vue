<template>
    <div class="piano">
        <div class="touche">
            <div class="blanche" id="c"></div>
            <div class="noir" id="cs">
                <span></span>
            </div>
            <div class="blanche" id="d"></div>
            <div class="noir" id="ds">
                <span></span>
            </div>
            <div class="blanche" id="e"></div>
            <div class="blanche" id="f"></div>
            <div class="noir" id="fs">
                <span></span>
            </div>
            <div class="blanche" id="g"></div>
            <div class="noir" id="gs">
                <span></span>
            </div>
            <div class="blanche" id="a"></div>
            <div class="noir" id="as">
                <span></span>
            </div>
            <div class="blanche" id="b"></div>
        </div>
        
    </div>
</template>

<style lang="postcss" scoped>

.piano {
    width: 500px;
    height: 252px;
    margin: 0 auto;
}

.touche {
    display: flex;
    background-color: #000;
    padding: 20px;
    height: 100%;
    position: relative;
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
}


</style>