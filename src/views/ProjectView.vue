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
    ".main-text",
    { opacity: [0, 1], y: [100, 0] },
    { duration: 1, easing: "ease-in-out" }
  );
  animate(
    ".construct",
    { opacity: [0, 1] },
    { duration: 1, delay: 1, easing: "ease-in-out" }
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
    class="h-screen w-screen overflow-hidden bg-[#FEB240] flex flex-col relative"
  >
    <div class="flex items-center justify-center md:justify-start p-12">
      <hr class="w-44 h-1 border-none bg-white hidden lg:inline-block" />
      <h1 class="text-white text-6xl ml-5 title-text">PROJECTS</h1>
    </div>

    <div class="flex w-full h-3/5 items-center justify-center flex-col">
      <img
        src="../assets/noto_construction.png"
        class="construct w-40 lg:w-[16rem]"
        alt=""
      />
      <p
        class="text-white text-xl text-center lg:text-5xl mt-10 lg:mt-24 description main-text px-5"
      >
        SOME WORK IS UNDER MAINTENANCE / ON PROGRESS
      </p>
    </div>

    <div class="flex w-full justify-between p-5 md:p-12 absolute bottom-0 cta">
      <AnimatedButton
        type="back"
        to="ABOUT ME"
        link="/about"
        class="text-[#FEB240]"
      ></AnimatedButton>
      <AnimatedButton
        type="next"
        to="CONTACTS"
        link="/contacts"
        class="text-[#FEB240]"
      ></AnimatedButton>
    </div>
  </div>
</template>
