<template>
    <div id="darkAndLightContainer">
        <img class="modeIcon" :src="iconSrc" />
        <button class="btnChangeMode" @click="toggleMode">Switch</button>
    </div>
</template>

<script>
let iconMode = "dark";

export default {
    name: "mode",
      data(){
        return {
            iconSrc: require("../assets/Icon/sun.svg")
            }
    },
    methods:{
        toggleMode() {
         if(iconMode === "dark" ){
            this.iconSrc = require("../assets/Icon/moon.svg") 
            iconMode = "light"
            this.lightMode()
        }else{
            this.iconSrc = require("../assets/Icon/sun.svg") 
            iconMode = "dark"
            this.darkMode()
        }
    },
    lightMode(){
        document.documentElement.style.setProperty('--corTitulo', '#2B283A');
        document.documentElement.style.setProperty('--corTexto', '#4A4E74');
        document.documentElement.style.setProperty('--corArea', '#F47D27');
        document.documentElement.style.setProperty('--cardBackground', '#F5F5F5');
        document.documentElement.style.setProperty('--socialsBackground', '#D5D4D8');
    },
    darkMode(){
        document.documentElement.style.setProperty('--corTitulo', '#F5F5F5');
        document.documentElement.style.setProperty('--corTexto', '#DCDCDC');
        document.documentElement.style.setProperty('--corArea', '#F3BF99');
        document.documentElement.style.setProperty('--cardBackground', '#1A1B21');
        document.documentElement.style.setProperty('--socialsBackground', '#161619');
    }
    }
    }

</script>
    <style>
    #darkAndLightContainer{
        background-color: var(--corTextoDark);
        width: 200px;
        height: 70px;
        display: flex;
        align-items: center;
        justify-content: space-around;
        border-radius: 10px;
        margin-bottom: 5px;
    }
    .modeIcon{
      height: 40px;
    }
    .btnChangeMode{
        width: 80px;
        height: 30px;
        border: none;
        border-radius: 5px;
        background-color: var(--socialsBackground);
        color: var(--corTitulo);
        font-family: var(--Main);
        font-weight: var(--bold);
    }
    </style>