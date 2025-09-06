<script setup lang="ts">
import type { EmblaCarouselType } from 'embla-carousel';

import emblaCarouselVue from 'embla-carousel-vue';

interface Testimonial {
  body: string;
  author: {
    name: string;
    handle: string;
    imageUrl: string;
  };
}

// Props
const props = defineProps<{
  testimonials: Array<Testimonial>;
}>();

// Embla setup
const [emblaRef, emblaApi] = emblaCarouselVue({ loop: true });

// State
const selectedIndex = ref<number>(0);
const canScrollNext = ref(false);
const canScrollPrev = ref(false);

// Next/prev actions
const scrollPrev = () => {
  emblaApi.value?.scrollPrev();
};;

const scrollNext = () => {
  emblaApi.value?.scrollNext();
};;

// ScrollTo method
const scrollTo = (index: number) => {
  emblaApi.value?.scrollTo(index);
};;

// Embla event handlers
const onSelect = (api: EmblaCarouselType) => {
  canScrollNext.value = api?.canScrollNext() || false;
  canScrollPrev.value = api?.canScrollPrev() || false;
  selectedIndex.value = api?.selectedScrollSnap() || 0;
};;

onMounted(() => {
  if (!emblaApi.value) {
    return;
  }

  emblaApi.value?.on('select', onSelect);
  emblaApi.value?.on('reInit', onSelect);
});
</script>

<template>
  <div ref="emblaRef" class="relative overflow-hidden">
    <div class="sm:text-[0] flex p-8">
      <div v-for="testimonial in testimonials" :key="testimonial.author.handle"
        class="pt-8 w-full sm:w-1/2 lg:w-1/3 px-4 flex-[0_0_100%] sm:flex-[0_0_50%] lg:flex-[0_0_33%]">
        <figure class="rounded-2xl p-8 text-sm/6 bg-white shadow-lg ring-1 ring-gray-900/5">
          <blockquote class="text-meivita-green-dark">
            <p>{{ `“${testimonial.body}”` }}</p>
          </blockquote>
          <figcaption class="mt-6 flex items-center gap-x-4">
            <!-- <img
                      class="size-10 rounded-full bg-gray-50"
                      :src="testimonial.author.imageUrl"
                      alt=""
                    /> -->
            <div>
              <div class="font-semibold text-meivita-green-dark">
                {{ testimonial.author.name }}
              </div>
            </div>
          </figcaption>
        </figure>
      </div>
    </div>
    <!-- <div class="absolute flex items-center justify-center gap-2 w-full p-2 bottom-0">
      <div v-for="(_, index) in testimonials" :key="index">
        <button class="h-2 w-2 rounded-full border border-black" :class="{ 'bg-black': index === selectedIndex }"
          @click="scrollTo(index)" />
      </div>
    </div> -->
    <button class="absolute flex items-center justify-center z-10 p-2 top-0 left-0 h-full" @click="scrollPrev">
      <Icon name="ph:caret-left" class="h-5 w-5 shrink-0" />
    </button>
    <button class="absolute flex items-center justify-center z-10 p-2 top-0 right-0 h-full" @click="scrollNext">
      <Icon name="ph:caret-right" class="h-5 w-5 shrink-0" />
    </button>
  </div>
</template>
