<template>
  <div>
    <div class="mesh-container">
      <client-only>
        <Pc></Pc>
      </client-only>
    </div>
    <div ref="titleWrapper" class="title-wrapper">
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

<script lang="ts">
export default {
  components: {
    Pc: () => {
      if(process.client) {
        return import('../components/pc.vue');
      }
    },
  }
}
</script>

<script setup lang="ts">
const toLinkedin = () => window.open("https://www.linkedin.com/in/mattia-bonardi-099b02235/","_blank");
const toInstagram = () => window.open("https://www.instagram.com/mattiaabonardi/", "_blank");
const toGitHub = () => window.open("https://github.com/mattiabonardi", "_blank");
const toMail = () => window.open('mailto:mattiabonardi99@gmail.com');
</script>

<style scoped>
body{
  pointer-events: none;
}
/** Background */
.mesh-container{
  position: fixed;
  z-index: -1;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  margin: 0;
  padding: 0;
  border: 0;
  pointer-events: none;
}

.title-wrapper {
  pointer-events: none;
  position: relative;
  padding: 0 75px 0;
  text-align: right;
  height: 60vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  opacity: 0.86;
  z-index: 5;
  opacity: 0.9;
  user-select: none; /* supported by Chrome and Opera */
   -webkit-user-select: none; /* Safari */
   -khtml-user-select: none; /* Konqueror HTML */
   -moz-user-select: none; /* Firefox */
   -ms-user-select: none; /* Internet Explorer/Edge */
}

.title{
  pointer-events: none;
  font-size: 40px;
  margin: 0;
  font-family: 'Lato', sans-serif;
  letter-spacing: 0.5px;
}

.subtitle{
  pointer-events: none;
  font-size: 20px;
  font-family: 'Lato', sans-serif;
}

.footer{
  height: 20vh;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 40px;
}

.social{
  cursor: pointer;
}

/** Desktop */
@media screen and (min-width: 992px) {
  .title-wrapper{
    padding: 0 200px 0;
  }

  .title{
    font-size: 100px;
  }

  .subtitle {
    font-size: 40px;
  }
}
</style>