<template>
  <!-- Background -->
  <div class="mesh-container"></div>
  <div class="title-wrapper">
      <h2 class="subtitle">I'm Mattia, a full stack</h2>
      <h1 class="title">DEVELOPER</h1>
  </div>
  <footer class="footer">
    <icon icon="instagram" size="20"></icon>
    <icon icon="github" size="20"></icon>
    <icon icon="linkedin" size="20"></icon>
    <icon icon="mail" size="20"></icon>
  </footer>
</template>

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
  font-weight: bold;
  margin: 0;
}

.subtitle{
  font-size: 20px;
}

.footer{
  height: 25vh;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 40px;
}
</style>