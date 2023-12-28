<script setup>
import AnimatedButton from "@/components/AnimatedButton.vue";
import ContactItem from "@/components/ContactItem.vue";
import { animate } from "motion";
import { onMounted, ref } from "vue";
import Indonesia from "@/assets/indonesia.png";
import Facebook from "@/assets/facebook.png";
import Instagram from "@/assets/ig.png";
import Spotify from "@/assets/spotify.png";
import Discord from "@/assets/discord.png";
import Github from "@/assets/github.png";
import Steam from "@/assets/steam.png";

const itemList = ref([
  {
    title: "(+62)815 6393 6568",
    img: Indonesia,
  },
  {
    title: "Vik Per",
    img: Facebook,
  },
  {
    title: "vkrprmn",
    img: Instagram,
  },
  {
    title: "ordinaryboy",
    img: Spotify,
  },
  {
    title: ".ordinaryboy",
    img: Discord,
  },
  {
    title: "vikripermana21",
    img: Github,
  },
  {
    title: "imag1ne",
    img: Steam,
  },
]);

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
    { opacity: [0, 1] },
    { duration: 1, easing: "ease-in-out" }
  );
  animate(
    ".grid-container",
    { opacity: [0, 1] },
    { duration: 1, delay: 1.5, easing: "ease-in-out" }
  );
  animate(
    ".cta",
    { opacity: [0, 1], y: [100, 0] },
    { delay: 1, duration: 0.5, easing: "ease-in-out" }
  );
  animate(".highlight", { width: [0, 1] }, { delay: 1, easing: "ease-in-out" });
});
</script>

<template>
  <div
    class="min-h-screen min-w-screen overflow-hidden bg-[#00BBF9] flex flex-col relative"
  >
    <div class="flex items-center justify-center md:justify-start p-12">
      <hr class="w-44 h-1 border-none bg-white hidden lg:inline-block" />
      <h1 class="text-white text-6xl ml-5 title-text">CONTACTS</h1>
    </div>

    <div class="flex w-full h-full items-center flex-col">
      <div class="relative">
        <span
          class="absolute h-3 lg:h-4 w-10/12 bg-[#38e3cc] highlight bottom-0 -right-7"
        ></span>
        <p
          class="text-xl md:text-2xl lg:text-4xl main-text text-white z-30 relative uppercase"
        >
          vikripermana91@gmail.com
        </p>
      </div>
      <div
        class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 w-full mb-16 p-5 lg:p-12 grid-container"
      >
        <template v-for="({ title, img }, key) in itemList" :key="key">
          <div class="flex justify-center items-center">
            <ContactItem :title="title" :image="img" :index="key" />
          </div>
        </template>
      </div>
    </div>

    <div class="flex w-full p-5 justify-between md:p-12 absolute bottom-0 cta">
      <AnimatedButton
        type="back"
        to="PROJECTS"
        link="/projects"
        class="text-[#00BBF9]"
      ></AnimatedButton>
      <AnimatedButton
        type="next"
        to="MAIN MENU"
        link="/main-menu"
        class="text-[#00BBF9]"
      ></AnimatedButton>
    </div>
  </div>
</template>
