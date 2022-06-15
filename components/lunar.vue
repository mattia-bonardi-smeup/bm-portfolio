<template>
  <div ref="globeContainer"></div>
</template>

<script setup lang="ts">
import { onMounted } from "@vue/runtime-core";
import * as THREE from "three";
import { ref } from "vue";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls.js"; 

const globeContainer = ref();

onMounted(() => {
  const scene = new THREE.Scene();
	const camera = new THREE.PerspectiveCamera( 75, window.innerWidth / window.innerHeight, 0.1, 1000 );

	const renderer = new THREE.WebGLRenderer();
	renderer.setSize( window.innerWidth, window.innerHeight );
	globeContainer.value.appendChild( renderer.domElement );

	// set light
	scene.add(new THREE.AmbientLight(0x333333));
	const light = new THREE.DirectionalLight(0xffffff, 1);
	light.position.set(5,3,5);
	scene.add(light);

	// create lunar object
	const lunarGeometry = new THREE.SphereGeometry(1, 32, 32);
	const lunarMaterial = new THREE.MeshToonMaterial({ 
		map: new THREE.TextureLoader().load("/textures/lunar.png"),
		bumpMap: new THREE.TextureLoader().load("/textures/lunar_bump.png")
	});
	const lunar = new THREE.Mesh( lunarGeometry, lunarMaterial );
	scene.add(lunar);

	camera.position.z = 3;

	// create controls
	const controls = new OrbitControls(camera, document.querySelector("title-wrapper"));
	controls.update();

	function animate() {
		controls.update();
		lunar.rotation.y += 0.001;
		requestAnimationFrame( animate );
		renderer.render( scene, camera );
	};

	animate();
});
</script>