<template>
  <Carousel :speed="3000" :list="list">
    <template v-slot="slotProps">
      <CarouselItem
        v-for="(item, index) in list"
        :key="index"
        :index="index"
        :currentIndex="slotProps.currentIndex"
        :speed="slotProps.speed"
      >
        <div :style="item" class="content-wrap flex items-center">
          <p class="flex items-center">Page {{ index + 1 }}</p>
        </div>
      </CarouselItem>
    </template>
  </Carousel>
</template>

<script>
import { Carousel, CarouselItem } from './components';

export default {
  name: 'App',

  components: {
    Carousel,
    CarouselItem,
  },

  data() {
    return {
      list: [
        {
          backgroundColor: '#3f51b5',
        },
        {
          backgroundColor: 'rgb(28 167 181)',
        },
        {
          backgroundColor: 'rgb(244, 67, 54)',
        },
        {
          backgroundColor: 'rgb(86 27 82)',
        },
      ],
    };
  },
};
</script>
