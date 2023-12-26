<script setup>
import { timeline } from "motion";
import { onMounted } from "vue";

onMounted(() => {
  const homeAnimate = [".home", { y: [2000, 0] }, { duration: 0.3 }];
  const infoAnimate = [
    ".info",
    { y: [-2000, 0] },
    { duration: 0.3, at: "<", delay: 0.1 },
  ];
  const projectAnimate = [
    ".project",
    { y: [2000, 0] },
    { duration: 0.3, at: "<", delay: 0.1 },
  ];
  const contactAnimate = [
    ".contact",
    { y: [-2000, 0] },
    { duration: 0.3, at: "<", delay: 0.1 },
  ];

  timeline([homeAnimate, infoAnimate, projectAnimate, contactAnimate], {
    direction: "alternate",
    duration: 1,
  });
});
</script>

<template>
  <div
    class="h-screen w-screen overflow-hidden bg-[#0649B5] flex justify-center items-center"
  >
    <div
      class="h-full flex-grow bg-[#9B5DE5] hover:w-96 w-0 transition-all flex justify-center items-center flex-col home"
    >
      <div
        class="p-10 rounded-full flex justify-center items-center border-4 border-white"
      >
        <i class="pi pi-home text-7xl text-white"></i>
      </div>
      <!-- <p class="text-white text-2xl">HOME</p> -->
    </div>
    <div
      class="h-full flex-grow bg-[#F15BB5] hover:w-96 w-0 transition-all justify-center items-center flex-col flex info"
    >
      <div
        class="p-10 rounded-full flex justify-center items-center border-4 border-white"
      >
        <i class="pi pi-info text-7xl text-white"></i>
      </div>
    </div>
    <div
      class="h-full flex-grow bg-[#FEB240] hover:w-96 w-0 transition-all justify-center items-center flex-col flex project"
    >
      <div
        class="p-10 rounded-full flex justify-center items-center border-4 border-white"
      >
        <i class="pi pi-list text-7xl text-white"></i>
      </div>
    </div>
    <div
      class="h-full flex-grow bg-[#00BBF9] hover:w-96 w-0 transition-all justify-center items-center flex-col flex contact"
    >
      <div
        class="p-10 rounded-full flex justify-center items-center border-4 border-white"
      >
        <i class="pi pi-phone text-7xl text-white"></i>
      </div>
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
