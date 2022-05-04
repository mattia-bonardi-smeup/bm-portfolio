<template>
  <div class="skillchip-wrapper">
    <img class="skillchip-icon" :src="src" />
    <h4 class="skillchip-text">{{text}}</h4>
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
    src.value = "/assets/icons/" + props.icon + ".svg";

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
  gap: 10px;
}

.skillchip-icon {
  height: 25px;
  width: auto;
}

.skillchip-text {
  font-size: 18px;
  margin: 0;
}
</style>