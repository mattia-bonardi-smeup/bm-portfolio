<template>
  <div class="skillchip-wrapper">
    <img class="skillchip-icon" :src="src" />
  </div>
</template>

<script lang="ts">import { Ref } from "vue";

export default {
  props: {
    icon: String,
    text: String
  },
  setup(props){
    const src: Ref<string> = ref();
    src.value = "/icons/" + props.icon + ".svg";

    return {
      src
    }
  }
}
</script>

<style scoped>
.skillchip-wrapper{
  display: flex;
  align-items: center;
}

.skillchip-icon {
  height: 25px;
  width: auto;
}
</style>