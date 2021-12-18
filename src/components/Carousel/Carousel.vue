<template>
  <div class="relative overflow-hidden">
    <div class="w-full slider-items">
      <slot v-bind:currentIndex="currentIndex" v-bind:speed="speed" />
    </div>
    <div class="flex items-center justify-center slider-indicator-wrap">
      <div
        v-for="(_, index) in list"
        :key="index"
        :class="`slider-indicator ${
          currentIndex === index && 'slider-indicator-active'
        }`"
        @click="moveSlide(index)"
      />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    list: {
      type: Array,
    },
    speed: {
      type: Number,
    },
  },

  data() {
    return {
      currentIndex: 0,
    };
  },

  methods: {
    moveSlide(index) {
      this.currentIndex = index;
    },
  },
};
</script>
