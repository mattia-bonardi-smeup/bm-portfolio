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
      <div class="skill-wrapper">
          <h2 class="skill-title">Back-End</h2>

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

.skill-wrapper{
  display: flex;
  justify-content: center;
  align-items: center;
}
.skill-title{
  font-family: "Lato",sans-serif;
  text-align: center;
  font-size: 30px;
}

</style>