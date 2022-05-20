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

      function animate() {
        //lunar.rotation.y += 0.001;
				requestAnimationFrame( animate );
				renderer.render( scene, camera );
			};

			animate();

			// rotate on mouse hover
			let lastMove = [window.innerWidth/2, window.innerHeight/2];

			function rotateOnMouseMove(e) {
				e = e || window.event;

				//calculate difference between current and last mouse position
				const moveX = ( e.clientX - lastMove[0]);
				const moveY = ( e.clientY - lastMove[1]);
				//rotate the globe based on distance of mouse moves (x and y) 
				lunar.rotation.y += ( moveX * .005);
				lunar.rotation.x += ( moveY * .005);

				//store new position in lastMove
				lastMove[0] = e.clientX;
				lastMove[1] = e.clientY;
			}

			document.addEventListener('mousemove', rotateOnMouseMove);
});
</script>