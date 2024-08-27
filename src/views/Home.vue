<template>
  <div id="app">
    <div id="card">
      <img src="../assets/User.svg">
      <Contato 
      nome="Laura Smith"
      area="Frontend Developer"
      site="laurasmith.com.br"
      />

      <Info
      title="About"
      text="
      I am a frontend developer with a particular interest in making 
      things simple and automating daily tasks. I try to keep up with
      security and best practices, and am always looking for new things to learn."
      />

      <Info
      title="Interests"
      text="
      Food expert. Music scholar. Reader. Internet fanatic. Bacon buff.
       Entrepreneur. Travel geek. Pop culture ninja. Coffee fanatic.
      "
      />

      <Socials />
    </div>
  </div>
</template>
<script>
import Contato from "@/components/contact.vue"
import Info from "@/components/info.vue"
import Socials from "@/components/socials.vue"

export default {
  name: "Home",
  components:{
    Contato,
    Info,
    Socials
  }
}
</script>
<style src="../css/style.css"></style>
