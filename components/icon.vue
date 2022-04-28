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
    },
    size: {
      type: String,
      default: "16"
    }
  },
  emits: ["iconClick"],
  setup(props, context) {
    const iconElement: Ref<HTMLElement> = ref();
    const iconStyle: ComputedRef<string> = computed(() => {
      return (
        "-webkit-mask: url(/icons/" +
        props.icon +
        ".svg) center center no-repeat;" +
        "width: " + props.size + "px;" +
        "height: " + props.size + "px;"
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
  background: #FFF;
}
</style>