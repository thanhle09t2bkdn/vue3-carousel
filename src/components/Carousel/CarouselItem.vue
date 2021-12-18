<template>
  <transition name="slide-fade">
    <div
      v-if="currentIndex === index"
      v-bind="$attrs"
      :style="{ transition: `all ${speed / 1000}s` }"
      class="absolute top-0 left-0 w-full slider-item"
    >
      <slot />
    </div>
  </transition>
</template>

<script>
export default {
  props: {
    index: {
      type: Number,
    },
    currentIndex: {
      type: Number,
    },
    speed: {
      type: Number,
    },
  },

  data() {
    return {
    };
  },
};
</script>
