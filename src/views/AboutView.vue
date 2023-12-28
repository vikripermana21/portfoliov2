<script setup>
import AnimatedButton from "@/components/AnimatedButton.vue";
import { animate } from "motion";
import { onMounted } from "vue";

onMounted(() => {
  animate(
    "hr",
    { opacity: [0, 1], x: [-100, 0] },
    { easing: "ease-in-out", duration: 1 }
  );
  animate(
    ".title-text",
    { opacity: [0, 1], x: [100, 0] },
    { duration: 1, easing: "ease-in-out" }
  );
  animate(
    ".description",
    { opacity: [0, 1], y: [100, 0] },
    { duration: 1, easing: "ease-in-out" }
  );
  animate(
    ".running-2",
    { opacity: [0, 1], x: [1000, 0] },
    { easing: "ease-in-out", duration: 1 }
  );
  animate(
    ".running-1",
    { opacity: [0, 1], x: [-1000, 0] },
    { easing: "ease-in-out", duration: 1 }
  );
  animate(
    ".cta",
    { opacity: [0, 1], y: [100, 0] },
    { delay: 1, duration: 0.5, easing: "ease-in-out" }
  );
});
</script>

<template>
  <div
    class="min-h-screen w-screen overflow-hidden bg-[#F15BB5] flex flex-col relative"
  >
    <div class="flex items-center justify-center md:justify-start p-12">
      <hr class="w-44 h-1 border-none bg-white hidden md:inline-block" />
      <h1 class="text-white text-6xl ml-5 title-text text-center">ABOUT ME</h1>
    </div>

    <div class="px-12 pb-12">
      <p
        class="text-white text-xl lg:text-3xl xl:text-4xl 2xl:text-5xl mt-5 description"
      >
        Meet the unstoppable learner, Vikri Permana! This English-speaking
        dynamo tackles challenges with unwavering grit, soaking up knowledge
        like a sponge. When work's done, he flips the switch to gamer mode,
        crushing opponents with strategic brilliance. But Vikri’s not all work
        and play; he chills out with a soundtrack of diverse tunes, sometimes
        even adding her own musical flair. A true force to be reckoned with,
        Vikri proves that curiosity, dedication, and a killer playlist are the
        perfect recipe for success.
      </p>
    </div>

    <div class="flex flex-col mt-5">
      <div class="relative flex overflow-hidden running-1">
        <div class="animate-marqueeright whitespace-nowrap">
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >HTML</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >CSS</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >JAVASCRIPT</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >C++</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >TYPESCRIPT</span
          >
        </div>

        <div class="absolute top-0 animate-marquee2right whitespace-nowrap">
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >HTML</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >CSS</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >JAVASCRIPT</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >C++</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >TYPESCRIPT</span
          >
        </div>
      </div>
      <div class="relative flex overflow-hidden mt-5 running-2 mb-28">
        <div class="animate-marqueeleft whitespace-nowrap">
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >NEXT</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >REACT</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >VUE</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >ANGULAR</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >FIGMA</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >LARAVEL</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >TAILWIND</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >MOTION ONE</span
          >
        </div>

        <div class="absolute top-0 animate-marquee2left whitespace-nowrap">
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >NEXT</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >REACT</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >VUE</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >ANGULAR</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >FIGMA</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >LARAVEL</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >TAILWIND</span
          >
          <span
            class="text-6xl lg:text-7xl 2xl:text-9xl text-white font-bold mx-4"
            >MOTION ONE</span
          >
        </div>
      </div>
      <div
        class="flex w-full justify-between p-5 md:p-12 absolute bottom-0 cta"
      >
        <AnimatedButton
          type="back"
          to="MAIN MENU"
          link="/main-menu"
          class="text-[#F15BB5]"
        ></AnimatedButton>
        <AnimatedButton
          type="next"
          to="PROJECTS"
          link="/projects"
          class="text-[#F15BB5]"
        ></AnimatedButton>
      </div>
    </div>
  </div>
</template>
