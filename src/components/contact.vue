<template>
    <div id="contatoContainer">
        <span class="name">{{ nome }}</span>
        <span class="area">{{ area }}</span>
        <span class="site">{{ site }}</span>
        <div class="links">
            <button class="btn email">
                <img class="contactIcon" src="../assets/Icon/Icon.svg">
                E-mail
            </button>
            <button class="btn linkedin">
                <img class="contactIcon" src="../assets/Icon/linkedin.svg">
                Linkedin
            </button>
        </div>
    </div>
</template>
<style src="../css/contact.css"/>
<script>
export default {
  name: 'Contato',
  props: {
    nome: String,
    area: String,
    site: String
  }
}
</script>