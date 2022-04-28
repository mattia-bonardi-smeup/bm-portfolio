<template>
  <div>
    <!-- Header -->
    <header class="header">
      <nav class="navbar">
        <div class="logo-wrapper">
          <a class="logo">BM.</a>
        </div>
        <div class="menu" :class="{active: isActive}" v-show="isActive">
          <div class="menu-item">ABOUT</div>
          <div class="menu-item">CONTACTS</div>
        </div>
        <div class="menu-button-wrapper">
          <icon class="menu-button" :icon="menuIcon" size="40" @iconClick="menuToggle"></icon>
        </div>
      </nav>
    </header>
    <NuxtPage />
  </div>
</template>

<script setup lang="ts">
import { Ref } from 'vue';

const isActive: Ref<boolean> = ref(false);
const menuIcon: Ref<string> = ref("menu");

const menuToggle = () => {
  console.log("toggle");
  if(isActive.value){
    // close menu
    isActive.value = false;
    menuIcon.value = "menu";
  }else{
    // open menu
    isActive.value = true;
    menuIcon.value = "close";
  }
}


</script>

<style>
html, body{
  color: #FFF;
  width: 100%;
  height: 100vh;
  margin: 0;
  padding: 0;
}

/** Header */
.header{
  width: 100%;
  display: flex;
  align-items: center;
  padding: 75px 35px 0px;
  box-sizing: border-box;
}

.navbar{
  width: 100%;
  display: flex;
  justify-content: space-between;
}

.logo-wrapper{
  display: flex;
  align-items: center;
}

.logo{
  font-size: 35px;
}

.menu{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 40px;
  visibility: hidden;
  z-index: 2;
  margin: 0;
  padding: 0;
  background-color: #121212;
  -webkit-animation: fadein 1s; /* Safari, Chrome and Opera > 12.1 */
  -moz-animation: fadein 1s; /* Firefox < 16 */
  -ms-animation: fadein 1s; /* Internet Explorer */
  -o-animation: fadein 1s; /* Opera < 12.1 */
  animation: fadein 1s;
}

.active{
  visibility: visible;
}

.menu-item{
  width: 100%;
  text-align: center;
  font-size: 20px;
}

.menu-button{
  position: relative;
  cursor: pointer;
  z-index: 300;
}


/** Animation keyframes */
@keyframes fadein {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* Firefox < 16 */
@-moz-keyframes fadein {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* Safari, Chrome and Opera > 12.1 */
@-webkit-keyframes fadein {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* Internet Explorer */
@-ms-keyframes fadein {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* Opera < 12.1 */
@-o-keyframes fadein {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>