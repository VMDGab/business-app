<template>
    <div id="darkAndLightContainer">
        <img class="modeIcon" :src="iconSrc" />
        <button class="btnChangeMode" @click="toggleMode">Switch</button>
    </div>
</template>

<script>
import sun from "../assets/Icon/sun.svg"
import moon from "../assets/Icon/moon.svg"
export default {
    name: "themeSwitcher",
      data(){
        return {
            currentMode: "dark",
            iconSrc: sun
            }
    },
    methods:{
        theme(){
            const styles = {
                dark: {
                '--corTitulo': '#2B283A',
                '--corTexto': '#4A4E74',
                '--corArea': '#F47D27',
                '--cardBackground': '#F5F5F5',
                '--socialsBackground': '#D5D4D8',
                },
                light:{
                '--corTitulo': '#F5F5F5',
                '--corTexto': '#DCDCDC',
                '--corArea': '#F3BF99',
                '--cardBackground': '#1A1B21',
                '--socialsBackground': '#161619',
                }
            };

            const selectedTheme = styles[this.currentMode]
            for(const [key, value] of Object.entries(selectedTheme)){
                document.documentElement.style.setProperty(key,value)
            }
            

        },

        toggleMode() {
            this.currentMode = this.currentMode == "dark" ? "light" : "dark"
            this.iconSrc =  this.currentMode == "dark" ? this.iconSrc = moon : this.iconSrc = sun 
            this.theme()
       },
    // lightMode(){
    //     this.iconSrc = moon 
    //     this.currentMode = "light"
    //     document.documentElement.style.setProperty('--corTitulo', '#2B283A');
    //     document.documentElement.style.setProperty('--corTexto', '#4A4E74');
    //     document.documentElement.style.setProperty('--corArea', '#F47D27');
    //     document.documentElement.style.setProperty('--cardBackground', '#F5F5F5');
    //     document.documentElement.style.setProperty('--socialsBackground', '#D5D4D8');
    // },
    // darkMode(){ 
    //     this.iconSrc = sun 
    //     this.currentMode = "dark"
    //     document.documentElement.style.setProperty('--corTitulo', '#F5F5F5');
    //     document.documentElement.style.setProperty('--corTexto', '#DCDCDC');
    //     document.documentElement.style.setProperty('--corArea', '#F3BF99');
    //     document.documentElement.style.setProperty('--cardBackground', '#1A1B21');
    //     document.documentElement.style.setProperty('--socialsBackground', '#161619');
    // }
    }
    }

</script>
    <style>
  
    #darkAndLightContainer{
        transition: all .5s ease-in-out;
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
        background-color: var(--corTexto);
        color: var(--cardBackground);
        font-family: var(--Main);
        font-weight: var(--bold);
        transition: all .5s ease-in-out;
        cursor: pointer;
    }
    </style>