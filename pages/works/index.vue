<template>
  <div>
    <div class="back-container"></div>
    <div class="container">
      <div class="work-container">
          <div class="work-title">
          Auth <br>Module
        </div>
        <div class="work-description">
          Collection of authentication functions for Node.js applications.
        </div>
        <div class="work-image-container">
          <img class="work-image" src="/images/authmodule.png" />
        </div>
        <div class="work-details">
          <div class="work-scope">
            Backend - 
          </div>
          <div class="technologies">
            <skill icon="node-js"></skill>
            <skill icon="typescript"></skill>
          </div>
        </div>
      </div>
      <div class="work-container">
        <div class="work-title">
          BM <br>Wiki
        </div>
        <div class="work-description">
          Personal wiki for any kind of use.
        </div>
        <div class="work-image-container">
          <img class="work-image" src="/images/bmwiki.png" />
        </div>
        <div class="work-details">
          <div class="work-scope">
            DevOps, Docs - 
          </div>
          <div class="technologies">
            <skill icon="wikijs"></skill>
            <skill icon="heroku"></skill>
          </div>
        </div>
      </div>
      <div class="work-container">
        <div class="work-title">
          Mini Light <br>Hub
        </div>
        <div class="work-description">
          Little web application for controlling a light bulb.
        </div>
        <div class="work-image-container">
          <img class="work-image" src="/images/minilighthub.png" />
        </div>
        <div class="work-details">
          <div class="work-scope">
            Full stack, IoT - 
          </div>
          <div class="technologies">
            <skill icon="html"></skill>
            <skill icon="css"></skill>
            <skill icon="javascript"></skill>
            <skill icon="c++"></skill>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">

</script>

<style scoped>
.back-container{
  position: fixed;
  z-index: -1;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  margin: 0;
  padding: 0;
  border: 0;
  background: -moz-linear-gradient(45deg, rgba(0,0,71,1) 0%, rgba(0,0,48,1) 32%, rgba(0,0,0,1) 100%);
  background: -webkit-linear-gradient(45deg, rgba(0,0,71,1) 0%, rgba(0,0,48,1) 32%, rgba(0,0,0,1) 100%);
  background: -o-linear-gradient(45deg, rgba(0,0,71,1) 0%, rgba(0,0,48,1) 32%, rgba(0,0,0,1) 100%);
  background: -ms-linear-gradient(45deg, rgba(0,0,71,1) 0%, rgba(0,0,48,1) 32%, rgba(0,0,0,1) 100%);
  background: linear-gradient(45deg, rgba(0,0,71,1) 0%, rgba(0,0,48,1) 32%, rgba(0,0,0,1) 100%); 
}

.container{
  width: 100%;
  padding: 60px 35px 0px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  gap: 100px;
}

.work-container{
  display: flex;
  flex-direction: column;
  gap: 30px;
  width: 100%;
}

.work-title{
  font-size: 55px;
}

.work-image-container{
  width: 100%
}

.work-image{
  max-width: 100%;
}

.work-details{
  display: flex;
  gap: 5px;
  justify-content: center;
  align-content: center;
}

.technologies{
  display: flex;
  align-content: center;
  justify-content: center;
}

/** Desktop */
@media screen and (min-width: 992px) {
  .container{
    padding: 50px 200px 0;
    flex-direction: row;
  }

  .work-container{
    gap: 25px;
  }
}
</style>