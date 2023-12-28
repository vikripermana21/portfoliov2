<script setup>
import { animate } from "motion";
import { ref } from "vue";
import { useRouter } from "vue-router";

defineProps(["to", "type", "link", "color"]);

const hoverButton = ref("");
const router = useRouter();

const animateIn = (name) => {
  hoverButton.value = name;
  animate(
    `.span-${name}`,
    {
      height: "150%",
      width: "200%",
    },
    {
      width: { delay: 0.3 },
    }
  );
  animate(`.text-${name}`, { opacity: [0, 1] }, { delay: 0.5, duration: 0.5 });
};
const animateOut = (name) => {
  animate(
    `.span-${name}`,
    {
      height: "100%",
      width: "4px",
    },
    {
      height: { delay: 0.3 },
    }
  );
  animate(`.text-${name}`, { opacity: 0 }, { delay: 0.5, duration: 0.5 });
  hoverButton.value = "";
};
</script>

<template>
  <div
    v-if="type === 'back'"
    class="flex items-center cursor-pointer relative"
    @mouseenter="animateIn('back')"
    @mouseleave="animateOut('back')"
    @click="router.push(link)"
  >
    <div
      class="w-1 border-none bg-white h-full absolute flex justify-center span-back items-center"
    >
      <p
        class="text-back text-xl lg:text-3xl"
        :class="$attrs.class"
        v-show="hoverButton == 'back'"
      >
        {{ to }}
      </p>
    </div>
    <p class="text-white text-xl lg:text-3xl ml-5">BACK</p>
  </div>
  <div
    v-if="type === 'next'"
    class="flex items-center cursor-pointer relative"
    @mouseenter="animateIn('next')"
    @mouseleave="animateOut('next')"
    @click="router.push(link)"
  >
    <div
      class="w-1 border-none bg-white h-full absolute flex justify-center span-next items-center right-0"
    >
      <p
        class="text-next text-xl lg:text-3xl"
        :class="$attrs.class"
        v-show="hoverButton == 'next'"
      >
        {{ to }}
      </p>
    </div>
    <p class="text-white text-xl lg:text-3xl mr-5">NEXT</p>
  </div>
</template>
