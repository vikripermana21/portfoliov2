<script setup>
import { animate } from "motion";

const props = defineProps(["title", "image", "index"]);

const animateIn = () => {
  animate(`.item-container-${props.index}`, { x: 10 });
};
const animateOut = () => {
  animate(`.item-container-${props.index}`, { x: 0 });
};
</script>

<template>
  <div
    class="bg-[#F15BB5] p-2 relative border-b-violet-600 border-[5px] border-r-0 border-l-0 border-t-0 w-full m-6 cursor-pointer item-container"
    :class="`item-container-${index}`"
    @mouseenter="animateIn"
    @mouseleave="animateOut"
  >
    <img :src="image" alt="" class="absolute right-2" />
    <p class="text-2xl pt-10 text-white">{{ title }}</p>
  </div>
</template>
