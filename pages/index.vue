<template>
  <div>
    <div class="mesh-container">
      <!--<Marble></Marble>-->
    </div>
    <div class="title-wrapper">
        <h2 class="subtitle">I'm Mattia, a full stack</h2>
        <h1 class="title">DEVELOPER</h1>
    </div>
    <footer class="footer">
      <icon class="social" icon="instagram" size="20" @click="toInstagram"></icon>
      <icon class="social" icon="github" size="20" @click="toGitHub"></icon>
      <icon class="social" icon="linkedin" size="20" @click="toLinkedin"></icon>
      <icon class="social" icon="mail" size="20" @click="toMail"></icon>
    </footer>
  </div>
</template>

<script setup lang="ts">
const toLinkedin = () => window.open("https://www.linkedin.com/in/mattia-bonardi-099b02235/","_blank");
const toInstagram = () => window.open("https://www.instagram.com/mattiaabonardi/", "_blank");
const toGitHub = () => window.open("https://github.com/mattiabonardi", "_blank");
const toMail = () => window.open('mailto:mattiabonardi99@gmail.com');
</script>

<style>
/** Background */
.mesh-container{
  position: fixed;
  z-index: -1;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  background-color: rgb(32, 33, 36);
}

.title-wrapper {
  padding: 0 75px 0;
  text-align: right;
  height: 60vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.title{
  font-size: 40px;
  margin: 0;
  font-family: 'Lato', sans-serif;
  letter-spacing: 0.5px;
}

.subtitle{
  font-size: 20px;
  font-family: 'Lato', sans-serif;
}

.footer{
  height: 25vh;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 40px;
}

.social{
  cursor: pointer;
}
</style>