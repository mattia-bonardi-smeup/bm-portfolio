<template>
  <div>
    <div class="mesh-container"></div>
    <div class="container">
      <div class="profile-image-wrapper">
        <img src="assets/images/profile.png" class="profile-image" />
        Berlin, 2022/02/21
      </div>
      <div class="section reveal">
        <div class="presentation">
          I'm Mattia Bonardi and I come from Italy. 
          I believe that each of us must never set limits. 
          Everyone must aspire to be the best version of themselves. 
          This is my vision and it's the reason why 
          I will always have the strength to listen and learn something new, 
          even if it does not belong to me completely.
        </div>
      </div>
      <div class="section reveal">
        <h2 class="section-title">Back End Skills</h2>
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
      <div class="section reveal">
        <h2 class="section-title">Front End Skills</h2>
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
      <div class="section reveal">
        <h2 class="section-title">Deployments Skills</h2>
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
      <div class="section reveal">
        <h2 class="section-title">Experience</h2>
        <div class="experience-wrapper">
          <div class="experience-element">
            <div class="experience-element-description">
              Smeup R&D - Full Stack Developer
            </div>
            <div class="experience-element-daterange">
              2020/12 - current
            </div>
          </div>
          <div class="experience-element">
            <div class="experience-element-description">
              Smeup R&D - Back End Developer (stage) - I developed a java microservice 
              (with Vert.X) which allows to interpret the Smeup DSL languages.
            </div>
            <div class="experience-element-daterange">
              2020/09 - 2020/12
            </div>
          </div>
          <div class="experience-element">
            <div class="experience-element-description">
              Smeup R&D - Back End Developer (stage) - I developed a software for 
              the control of a hydroponic station.
            </div>
            <div class="experience-element-daterange">
              2019/06 - 2019/08
            </div>
          </div>
          <div class="experience-element">
            <div class="experience-element-description">
              Software Design & Web Development student at JobsAcademy
            </div>
            <div class="experience-element-daterange">
              2018/08 - 2020/12
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const reveal = () => {
  var reveals = document.querySelectorAll(".reveal");

  for (var i = 0; i < reveals.length; i++) {
    var windowHeight = window.innerHeight;
    var elementTop = reveals[i].getBoundingClientRect().top;

    if (elementTop < windowHeight) {
      reveals[i].classList.add("reveal-active");
    } else {
      reveals[i].classList.remove("reveal-active");
    }
  }
}

onMounted(() => {
  window.addEventListener('scroll', reveal);
});
</script>

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
  background-color: #121212;
}

.container{
  width: 100%;
  padding: 0px 35px 0px;
}

.profile-image-wrapper{
  display: flex;
  justify-content: center;
  height: calc(100vh - 116px);
  width: 100%;
  flex-direction: column;
  -webkit-animation: fadein 3s; /* Safari, Chrome and Opera > 12.1 */
  -moz-animation: fadein 3s; /* Firefox < 16 */
  -ms-animation: fadein 3s; /* Internet Explorer */
  -o-animation: fadein 3s; /* Opera < 12.1 */
  animation: fadein 3s;
  font-style: italic;
}

.profile-image{
  max-width: 100%;
}

.section{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100vh;
}

.presentation{
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  height: 100vh;
  font-size: 24px;
}

.section-title{
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

.experience-wrapper{
  display: flex;
  flex-direction: column;
  gap: 30px;
}
.experience-element{
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.experience-element-description{
  text-align: left;
  width: 75%;
}

.experience-element-daterange{
  text-align: right;
}

</style>