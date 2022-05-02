<template>
  <header class="header">
    <nav class="navbar">
      <div class="logo-wrapper">
        <NuxtLink class="logo" to="/">BM.</NuxtLink>
      </div>
      <div class="menu" :class="{active: isActive}">
        <a class="menu-item" @click="changePage('/about')">ABOUT</a>
      </div>
      <div class="menu-button-wrapper">
        <icon class="menu-button" :icon="menuIcon" size="40" @iconClick="menuToggle"></icon>
      </div>
    </nav>
  </header>
</template>

<script setup lang="ts">
import { Ref } from 'vue';

const router = useRouter();

const changePage = (route: string) => {
  isActive.value = false;
  menuIcon.value = "menu";
  router.push(route);
}

const isActive: Ref<boolean> = ref(false);
const menuIcon: Ref<string> = ref("menu");

const menuToggle = () => {
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
  cursor: pointer;
  font-family: 'Lato', sans-serif;
  letter-spacing: 2px;
  text-decoration: none;
  color: white;
}

.menu{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  flex-direction: column;
  justify-content: center;
  gap: 40px;
  display: none;
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
  display: flex;
}

.menu-item{
  width: 100%;
  text-align: center;
  font-size: 20px;
  cursor: pointer;
}

.menu-button{
  position: relative;
  cursor: pointer;
  z-index: 300;
}

/** Desktop */
@media screen and (min-width: 992px) {
  .header{
    padding: 75px 125px 0px;
  }

  .menu-button-wrapper{
    display: none;
  }

  .menu{
    position: unset;
    display: flex;
    height: auto;
    background-color: transparent;
    flex-direction: row;
    justify-content: right;
    align-items: center;
    gap: 20px;
  }

  .menu-item{
    width: auto;
    padding: 3px;
  }
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