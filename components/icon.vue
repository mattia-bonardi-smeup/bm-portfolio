<template>
  <div class="icon" :style="iconStyle" @click="onClick"></div>
</template>

<script lang="ts">
import { computed, ComputedRef, Ref, ref } from "vue";
export default {
  props: {
    icon: {
      type: String,
      default: null,
    }
  },
  emits: ["iconClick"],
  setup(props, context) {
    const iconElement: Ref<HTMLElement> = ref();
    const iconStyle: ComputedRef<string> = computed(() => {
      return (
        "-webkit-mask: url(/icons/" +
        props.icon +
        ".svg) center center no-repeat;"
      );
    });
    const onClick = () => {
      context.emit("iconClick");
    };
    return {
      iconElement,
      iconStyle,
      onClick,
    };
  },
};
</script>

<style>
.icon {
  background: #000;
  height: 20px;
  max-width: 20px;
}
</style>