<template>
  <div>
    <div class="mesh-container"></div>
    <div class="container">
      <div class="profile-image-wrapper">
        <img src="assets/images/profile.png" class="profile-image" />
      </div>
      <div class="description">
        I'm Mattia Bonardi and I come from Italy. 
        I believe that each of us must never set limits. 
        Everyone must aspire to be the best version of themselves. 
        This is my vision and it's the reason why 
        I will always have the strength to listen and learn something new, 
        even if it does not belong to me completely.
      </div>
      <div class="skills-section">
        <h2 class="skills-title">Back End Skills</h2>
        <div class="skills-wrapper">
          <div class="skills-row">
            <skillchip icon="node-js" text="Node js"></skillchip>
            <skillchip icon="vitejs" text="Vite js"></skillchip>
          </div>
          <div class="skills-row">
            <skillchip icon="java" text="Java EE"></skillchip>
            <skillchip icon="vertx" text="Vert.X"></skillchip>
            <skillchip icon="spring-boot" text="Spring Boot"></skillchip>
          </div>
          <div class="skills-row">
            <skillchip icon="mongo" text="Mongo"></skillchip>
            <skillchip icon="mysql" text="MySql"></skillchip>
            <skillchip icon="redis" text="Redis"></skillchip>
            <skillchip icon="firebase" text="Firebase"></skillchip>
          </div>
          <div class="skills-row">
            <skillchip icon="nginx" text="Nginx"></skillchip>
            <skillchip icon="as400" text="As400"></skillchip>
            <skillchip icon="c++" text="C++"></skillchip>
          </div>
        </div>
      </div>
      <div class="skills-section">
        <h2 class="skills-title">Front End Skills</h2>
        <div class="skills-wrapper">
          <div class="skills-row">
            <skillchip icon="nuxt" text="Nuxt js"></skillchip>
            <skillchip icon="vue-js" text="Vue js"></skillchip>
            <skillchip icon="electron" text="Electron js"></skillchip>
          </div>
          <div class="skills-row">
            <skillchip icon="html" text="HTML5"></skillchip>
            <skillchip icon="css" text="CSS3"></skillchip>
          </div>
          <div class="skills-row">
            <skillchip icon="typescript" text="Typescript"></skillchip>
            <skillchip icon="javascript" text="Javascript"></skillchip>
          </div>
        </div>
      </div>
      <div class="skills-section">
        <h2 class="skills-title">Deployments Skills</h2>
        <div class="skills-wrapper">
          <div class="skills-row">
            <skillchip icon="docker" text="Docker"></skillchip>
            <skillchip icon="vmware" text="vmware"></skillchip>
            <skillchip icon="heroku" text="Heroku"></skillchip>
          </div>
          <div class="skills-row">
            <skillchip icon="ubuntu" text="Ubuntu"></skillchip>
            <skillchip icon="opensuse" text="OpenSuse"></skillchip>
            <skillchip icon="raspberry-pi" text="Raspberry Pi"></skillchip>
          </div>
          <div class="skills-row">
            <skillchip icon="lambda" text="AWS Lambda"></skillchip>
            <skillchip icon="s3" text="AWS S3"></skillchip>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
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
  background-color: black;
}

.container{
  width: 100%;
  padding: 50px 35px 0px;
}

.profile-image-wrapper{
  width: 100%;
}

.profile-image{
  max-width: 100%;
}

.description{
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  height: 100vh;
  font-size: 24px;
}

.skills-section{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100vh;
}
.skills-title{
  font-family: "Lato",sans-serif;
  text-align: center;
  font-size: 35px;
}

.skills-wrapper{
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.skills-row{
  display: flex;
  align-content: center;
  justify-content: center;
  gap: 10px;
}

</style>