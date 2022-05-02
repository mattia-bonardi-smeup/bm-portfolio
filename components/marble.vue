<template>
  <div ref="globeContainer"></div>
</template>

<script lang="ts">
import { onMounted } from "@vue/runtime-core";
import Globe, { GlobeInstance } from "globe.gl";
import { ref } from "vue";

export default {
  setup() {
    const globeContainer = ref();

    onMounted(() => {
      const globe: GlobeInstance = Globe({ animateIn: true });
      globe(globeContainer.value as HTMLDivElement)
        .globeImageUrl("images/marble.jpg")
        .backgroundImageUrl("images/sky.png");
      (globe.controls() as any).autoRotate = true;
      (globe.controls() as any).autoRotateSpeed = 0.6;
    });

    return {
      globeContainer,
    };
  },
};
</script>