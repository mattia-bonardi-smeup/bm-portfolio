<template>
  <div>
    <div ref="threeContainer" class="three-container">
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

<script setup lang="ts">
import { onMounted } from "@vue/runtime-core";
import * as THREE from "three";
import { ref } from "vue";
import SplineLoader from '@splinetool/loader';
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls.js"; 

const toLinkedin = () => window.open("https://www.linkedin.com/in/mattia-bonardi-099b02235/","_blank");
const toInstagram = () => window.open("https://www.instagram.com/mattiaabonardi/", "_blank");
const toGitHub = () => window.open("https://github.com/mattiabonardi", "_blank");
const toMail = () => window.open('mailto:mattiabonardi99@gmail.com');

const threeContainer = ref();
const titleWrapper = ref();

onMounted(() => {
	// camera
	const camera = new THREE.OrthographicCamera(window.innerWidth / - 2, window.innerWidth / 2, window.innerHeight / 2, window.innerHeight / - 2,  -50000, 50000);
	camera.position.set(40.96, 1.22, 1000);
	camera.quaternion.setFromEuler(new THREE.Euler(0, 0, 0));

	// scene
	const scene = new THREE.Scene();

	// spline scene
	const loader = new SplineLoader();
	loader.load(
		'3d/pc.splinecode',
		(splineScene) => {
			scene.add(splineScene);
		}
	);

	// renderer
	const renderer = new THREE.WebGLRenderer({ antialias: true });
	renderer.setSize(window.innerWidth, window.innerHeight);
	renderer.setAnimationLoop(animate);
	threeContainer.value.appendChild(renderer.domElement);

	// scene settings
	renderer.shadowMap.enabled = true;
	renderer.shadowMap.type = THREE.PCFShadowMap;

  renderer.setClearAlpha(1);
  
  // orbit controls
	const controls = new OrbitControls(camera, titleWrapper.value);
	controls.enableDamping = true;
	controls.dampingFactor = 0.125;

	window.addEventListener('resize', onWindowResize);
	function onWindowResize() {
		camera.left = window.innerWidth / - 2;
		camera.right = window.innerWidth / 2;
		camera.top = window.innerHeight / 2;
		camera.bottom = window.innerHeight / - 2;
		camera.updateProjectionMatrix();
		renderer.setSize(window.innerWidth, window.innerHeight);
	}

	function animate(time) {
    renderer.render(scene, camera);
    controls.update();
	}
	});
</script>

<style scoped>
body{
  pointer-events: none;
}
/** Background */
.three-container{
  position: fixed;
  z-index: -1;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  margin: 0;
  padding: 0;
  border: 0;
}

.title-wrapper {
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