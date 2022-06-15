<template>
  <div ref="globeContainer"></div>
</template>

<script setup lang="ts">
import { onMounted } from "@vue/runtime-core";
import * as THREE from "three";
import { ref } from "vue";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls.js"; 
import SplineLoader from '@splinetool/loader';

const globeContainer = ref();

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
	globeContainer.value.appendChild(renderer.domElement);

	// scene settings
	renderer.shadowMap.enabled = true;
	renderer.shadowMap.type = THREE.PCFShadowMap;

	renderer.setClearAlpha(1);

	// orbit controls
	const controls = new OrbitControls(camera, globeContainer.value);
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
		controls.update();
		renderer.render(scene, camera);
	}
	});
</script>