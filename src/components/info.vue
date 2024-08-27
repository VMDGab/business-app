<template>
    <div id="info">
        <span class="title">{{ title }}</span>
        <span class="text">{{ text }}</span>
    </div>
</template>
<style src="../css/info.css"/>
<script>
export default {
    name: "Info",
    props:{
        title: String,
        text: String
    }
}
</script>