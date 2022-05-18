<template>
  <div ref="globeContainer"></div>
</template>

<script setup lang="ts">
import { onMounted } from "@vue/runtime-core";
import * as THREE from "three";
import { ref } from "vue";

const globeContainer = ref();

onMounted(() => {
  const scene = new THREE.Scene();
			const camera = new THREE.PerspectiveCamera( 75, window.innerWidth / window.innerHeight, 0.1, 1000 );

			const renderer = new THREE.WebGLRenderer();
			renderer.setSize( window.innerWidth, window.innerHeight );
			globeContainer.value.appendChild( renderer.domElement );

			const geometry = new THREE.SphereGeometry( 15, 32, 16 );
			const material = new THREE.MeshBasicMaterial({ 
        map: new THREE.TextureLoader().load("/assets/textures/lunar.png")
      });
			const lunar = new THREE.Mesh( geometry, material );
			scene.add(lunar);

			camera.position.z = 50;

      function animate() {
        lunar.rotation.y += 0.001;
				requestAnimationFrame( animate );
				renderer.render( scene, camera );
			};

			animate();
});
</script>